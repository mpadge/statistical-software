## Scrape the Abstracts

This code gets the number of papers for each volume:

``` r
library (magrittr)
num_papers <- function (volume = 13) {
    u <- paste0 ("https://www.jstatsoft.org/issue/view/v",
                 sprintf ("%03d", volume))
    x <- xml2::read_html (u)

    # content is sometimes only Articles, but other times Articles, Reviews,
    # Technical Notes, and other categories. Each of this is delineated by
    # a simple div:tocSectionTitle, so these need to be identified, and content
    # parsed only for "Articles".
    content <- rvest::html_nodes (x, "#content") %>%
        rvest::html_children ()
    index <- grep ("tocSectionTitle", rvest::html_attrs (content))
    divs <- rvest::html_text (content [index])
    articles <- grep ("Articles", divs)
    if (articles == 1 & length (index) > 1) {
        content <- content [(index [1] + 1):(index [2] - 1)]
    } else if (articles == length (divs)) {
        content <- content [(index [articles] + 1):length (content)]
    } else {
        content <- content [(index [articles] + 1):(index [articles + 1] - 1)]
    }
    content <- content [grep ("tocArticle", content)]

    #td <- rvest::html_nodes (x, "td") %>%
    #    rvest::html_attrs () %>%
    #    unlist () %>%
    #    unname ()
    #length (which (td == "tocTitle"))
    return (length (content))
}
volume <- 1
npapers <- num_papers (volume)
message ("Volume ", volume, " has ", npapers, " papers")
```

    ## Volume 1 has 4 papers

This extracts the title and abstract for one paper:

``` r
get_abstract <- function (volume = 13, paper = 1) {
    u <- paste0 ("https://www.jstatsoft.org/index.php/jss/article/view/v",
                 sprintf ("%03d", volume), "i", sprintf ("%02d", paper))
    x <- xml2::read_html (u)
    # The 2 fields are embedded in meta:
    title <- rvest::html_nodes (x, "meta[name='description']") %>%
        rvest::html_attr ("content")
    abstract <- rvest::html_nodes (x, "meta[name='DC.Description']") %>%
        rvest::html_attr ("content")
    date <- rvest::html_nodes (x, "meta[name='DC.Date.issued']") %>%
        rvest::html_attr ("content")

    # alternative: Extract from body - some volumes/papers don't have the meta:
    if (nchar (abstract) == 0 | nchar (title) == 0) {
        txt <- rvest::html_nodes (x, "td") %>%
            rvest::html_text ()
        title <- txt [grep ("^Title:", txt) + 1]
        abstract <- txt [grep ("^Abstract:", txt) + 1]
    }

    # Volume 76 has final 2 articles with non-standard URLs which fail here
    ret <- NULL
    if (length (abstract) > 0 | length (title) > 0) {
        ret <- list (title = title,
                     abstract = abstract,
                     date = date)
    }
    return (ret)
}
get_abstract (1, 3)
```

    ## $title
    ## [1] "XLISP-Stat Tools for Building Generalised Estimating Equation Models"
    ## 
    ## $abstract
    ## [1] "This paper describes a set of Lisp-Stat tools for building Generalised Estimating Equation models to analyse longitudinal or clustered measurements. The user interface is based on the built-in regression and generalised linear model prototypes, with the addition of object-based error functions, correlation structures and model formula tools. Residual and deletion diagnostic plots are available on the cluster and observation level and use the dynamic graphics capabilities of Lisp-Stat."
    ## 
    ## $date
    ## [1] "1996-08-16"

Get the current—and therefore maximal—volume number:

``` r
current_vol <- function () {
    u <- "https://www.jstatsoft.org/issue/archive"
    x <- xml2::read_html (u)
    n <- rvest::html_nodes (x, "div[id='issues']") %>%
        rvest::html_nodes ("div[id]") %>%
        rvest::html_attrs () %>%
        unlist () %>%
        unname ()
    as.integer (gsub ("issue-", "", n [grep ("issue-", n)]) [1])
}
current_vol ()
```

    ## [1] 91

Get all abstracts:

``` r
#get_all_abstracts <- function () {
    vmax <- current_vol ()
    res <- tibble::tibble (date = character (),
                           volume = integer (),
                           number = integer (),
                           title = character (),
                           abstract = character ())

    pb <- utils::txtProgressBar (style = 3)
    for (i in seq (vmax)) {
        n <- num_papers (i)
        for (j in seq (n)) {
            a <- get_abstract (i, j)
            if (!is.null (a)) {
                res <- rbind (res, tibble::tibble (date = a$date,
                                                   volume = i,
                                                   number = j,
                                                   title = a$title,
                                                   abstract = a$abstract))
            }
        }
        utils::setTxtProgressBar (pb, i / vmax)
    }
    close (pb)

    return (res)
#}
#a <- get_all_abstracts ()
saveRDS (res, file = "jss-abstracts.Rds")
```

## Analyses

These presume all of the above to have been run, and a local
`"jss-abstracts.Rds"` file to have been created.

``` r
a <- readRDS ("jss-abstracts.Rds")
d <- quanteda::dfm (a$abstracts)
s <- sort (quanteda::colSums (d), decreasing = TRUE)
sp0 <- spacyr::spacy_parse (names (s))
getnoun <- function (pos, token) {
    if (length (pos) > 2 & pos [length (pos)] == "NOUN")
        return (token [length (token)])
    else if (length (pos) <= 2)
        return (paste0 (token, collapse = " "))
    else
        return (token [pos == "NOUN"] [1])
}
sp <- sp0 %>%
    dplyr::group_by (doc_id) %>%
    dplyr::summarise (noun = getnoun (pos, token))
index <- match (unique (sp0$doc_id), sp$doc_id)
nouns <- sp$noun [index]
nouns [is.na (nouns)] <- names (s) [is.na (nouns)]

names (s) <- nouns
s <- data.frame (noun = names (s),
                 n = as.integer (s),
                 stringsAsFactors = FALSE) %>%
    dplyr::group_by (noun) %>%
    dplyr::summarise (n = sum (n)) %>%
    dplyr::arrange (desc (n))

for (i in nouns)
{
    index <- grep (i, s$noun)
    s$n [index [1]] <- sum (s$n [index])
    if (length (index) > 1)
    {
        index2 <- seq (nrow (s)) [!seq (nrow (s)) %in% index [-1] ]
        s <- s [index2, ]
    }
}
s <- dplyr::arrange (s, desc (n))
```