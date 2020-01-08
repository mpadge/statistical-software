# What is (open-source) statistical software and how can it be validated, tested, and reviewed?

A repo of ideas and explorations for rOpenSci’s project on peer-reviewed
statistical software. The current form of this document summarises
results from attempts to *empirically* define the concepts that follow,
in the belief that initial attempts at definition should be as empirical
reproducible and defensible as possible, to allow a maximally neutral
initial assessment prior to posterior, subjective modification. The
document presents four primary aspects, and sub-aspects within each, in
a linear sequential order, and treats each as an independent unit. There
will of course be many inter-dependencies between these units.

# 1\. Peer Review

Important Questions:

  - What is Peer Review?
  - How can a system of peer review best be constructed *ab initio*?
  - How can a system of peer review be cultivated and maintained? (That
    component directly connects to the final Community component
    considered below)
  - At what points does peer review start and end? (That component
    directly relates to the issue of software life cycles considered
    below)
  - Related to the previous question: Is peer-review a one-off
    phenomenon, or should there be some degree of ongoing engagement?
  - To the extent that ongoing engagement may be considered desirable,
    how can we best ensure the ongoing *independence* of peer review
    from the development itself? Is that even possible? (Some of the
    only role models for such appear to be external peer-review of code,
    for which independent auditing bodies are widely available, the
    functions of which are generally *not* transferable to the current
    context of peer-reviews of open-source code.)

# 2\. Statistical Software

## 2.1 Summary

The project requires a degree of consensus on the scope of “Statistical
Software”. One of the primary, coherent bodies of reference for
statistical software is the eponymous [academic
journal](https://www.jstatsoft.org). The following summarises detailed
explorations in a [sub-directory of this
repository](https://github.com/mpadge/statistical-software/tree/master/jss),
involving code to extract and analyse the abstracts of all articles
published by the Journal of Statistical Software. Textual descriptions
of statistical software are very generic and homogeneous, and have
become more so over time, most notably from around 2008 onwards. It is
therefore difficult to apply standard “text mining” algorithms to
discern topics, clusters, or other textual phenomena which might help to
distinguish categories of statistical software. The following
nevertheless provides a brief list of nouns which define potentially
distinct topics within the broader realm of statistical software:

## 2.2 Terms Defining Statistical Software (from JSS Abstracts)

### 2.2a Applications

1.  paleo, ecosystems, sediment, fossil, pollution, water, diatom,
    acidifation
2.  genealogy, varieties, branches, cultivars,
3.  ordination, migrants, pioneering, kendall, infections, dyads,
    disorders, lifestyle, susceptibility, nucleotide, polymorphisms,
    chromosome, cofactors, proteins, organism, liquid chromatography,
    compensation, bioreactors, substrates, carbon, lymph

### 2.2b General Statistics

1.  model(s), data, user(s), program, analysis, code, regression,
    linear, error, cluster(ing), likelihood, matrix, estimates, effects,
    multivariate, distributions, language, survival, time, distribution,
    simulation, optimal, density, information, classification, test,
    response, estimation, parameter, risk,, effect, comparison, sample,
    markov chain, monte carlo, optimization, population, imputation
2.  quality, processes, ratio, web, computer, poisson, disease, graph,
    area densities, gamma, dirichlet, factor, bayes, interval, length,
    simulations, estimator, groups, wavelet, individual, dimension
    reduction, plot, inverse, principal, table, value, decomposition,
    species, group, curve, covariate, accuracy, dose, pattern, feature,
    threshold, anova, hazard map, subjects, panel, field, odds
3.  concentration, observation, step, failure, cause, patient, origin,
    variate, region, loss, run, gibbs, combinations, contrast, behavior,
    complexity, coefficient, priors, stage, splines, phase, batch,
    shape, tail, element, decision, cost, resolution, log, rank,
    iterative, trait, haplotype, location, gradient, domain, array,
    reduce, skew, trajectories, variation, intervention, voxels,
    maximization, expectation, escalation, cytometry, randomization,
    genotype
4.  nonstationarity, implemenation, kaufman, calibrate, likelikhood,
    loading, candidates, travel, consumers, manipulations, hyper,
    coordination, majorization, covariation, tract, norms,
    microstructure, imbalances, registers, optimizes, proof, supervisor,
    dendrograms, organisation, saturation, convexity, geophysics
5.  bounds, script, pearson, deviance, generator, macros, term, lattice,
    researcher, fourier, product, mode, similarity, consistency, box,
    spline, education, intensity, situation, goal, partition, surface,
    path, attribute, entries, combine, tails
6.  install, year, separation, folds, censoring, scoring, symmetry,
    mantel, forward, occurrence, passing, zeros, width, art, score,
    author, voting, pca, indicator, parent, rule, pair, turn, products,
    correction, circular, physical, orders, magnitude, sunspot,
    autoregression, inflation, fisher, impute, split, marker, equality,
    membership, derivative, moment, chromatograms, cloud, spread,
    ridges, identity

### 2.2c Special Issues

1.  ihaka, gentleman, redesign, reimplementation, respond, stimuli,
    visibility, obstruction, probabilites, rcppeigen, eigen,
    eddelbuettel, mosaicplots, spineplots, ceiling, shadings, palettes,
    pngs, overlay, hotspot, oscillation, teleconnections,
    microsimulation, businesses, microdatasets, inequalities,
    celebrates, anniversary, festschrift, chair, accomplishments, guest,
    editors, reproduction, cohorts, hosts, retrieval, completing

### 2.2d Miscellaneous terms beyond the above clusters

1.  multifactor, hyperparameter, concentrates, gauss, tukey,
    congruential, modulus, fibonacci, cryptography, infer, geography,
    obstacle, bayesians, nuances, jackknifed, respondent,
    cheminformatics, microscopy, nanosecond, spectrochromatograms,
    elution, analytes, imperfections, observatory, terabyte, inverses,
    wildlife, policies, underestimation, accelerations, biodiversity,
    dispense, salesman, vehicle, presenceabsence, percent, reactions,
    neuropsychology, implemantation, transversal, discordance, benefit,
    refinement, metaheuristics, district, irregularities, saddlepoints,
    discontinuities, hygiene, agents, vocabulary, critics, weaknesses,
    demographers, actuaries, photovoltaics, incident, feathers, flight,
    insurances, portfolios, decomposes, ultimatum game, chunks, queries,
    pressure, materials, subclasses, longitudes, latitudes, outbreaks,
    runtimes, origins, biometrics, overlaps, career, monograph,
    expectancy, pyramids, ergonomics, clothing, workstation, ontologies,
    plasma, clearance, humans, generalisation, violates, myocardial
    infarction, aesthetics, heritability, declaration,
    parameterizations, tensors, wraps, differentiates, archives,
    geology, continuum, ingredient

## 2.3 Approaches to Defining Statistical Software

While the preceding terms might help somewhat to attempt a definition of
“Statistical Software”, there is clearly going to be a need to
subjectively define what the scope of such might be. The Journal of
Statistical Software simply defines [its own
scope](https://www.jstatsoft.org/pages/view/mission) as,

> statistical computing in all areas of empirical research,

presumably leaving the task of defining the boundaries of scope to *ad
hoc* decisions. We note only that conventional (sociological) attempts
at defining culturally shared concepts are generally approached via
surveys along the lines of lists of potential topics which participants
are asked to allocate to within or beyond definition or scope. Scope is
then readily defined through (probabilistically) demarcating all items
adjudged as “beyond scope”.

## 2.4 Difficulties in Defining/Delieating Statistical Software

While this document will not (currently) attempt to provide any
definitions of “statistical software”, it is nevertheless instructive to
consider a few “edge cases” which illustrate the potential difficulties
faced in attempting such definition. The following brief digressions are
made with reference to the “fitness” of statistical software for some
particular purpose, by which is meant any and all potential definitions
of applicability, validity, accuracy, or similar concepts.

### 2.4a Artificial Intelligence Algorithms

Artificial Intelligence (AI) algorithms have become deeply embedded
within many areas of modern computational science, and certainly can not
be excluded from an (increasingly?) active role in statistical software.
Yet AI algorithms present an immediate challenge to two of the surest
measures of the “fitness” of statistical software: (i) They are very
generally unable to generate reproducible results; and (ii) they almost
always suffer from some form of bias, particularly as generated by a
necessarily incomplete set of training data. At the risk of
over-simplification, it may be simply stated that AI algorithms may
generally not be presumed to generate either reproducible or unbiased
results (absent some kind of explicit and external demonstration of such
absence). Yet such inability can not exclude such software from
consideration as a valid form of “statistical software,” rather these
issues illustrate the need to adapt any specifications or definitions to
particular cases.

### 2.4b Genetic Algorithms

Similar to AI algorithms, genetic algorithms can not be excluded from
the domain of “statistical software”, yet their results may also
generally not be precisely predictable for any given input, and so they
may not be considered to generate truly reproducible results.

### 2.4c Clustering Algorithms and their Relations

Clustering Algorithms are included here as a synecdoche for the general
class of techniques which can not fail to generate an intelligible
output, entirely regardless of the validity or otherwise of that output.
Clustering algorithms must generate a result, yet that result may be
entirely devoid of meaning or significance. Yet clustering algorithms
are also an integral part of contemporary statistics, and can not be
excluded from consideration. This suggests in turn that statistical
software must consider implementations which are potentially unable to
generate meaningful output.

### 2.4d Summary

The following table summarises these three brief classes of statistical
software, and the potential problems they encapsulate, where “No” is to
be interpreted to imply “Not necessarily”, and “Yes” merely some
sufficient degree of surety.

| Algorithm  | Reproducible? | Unbiased? | Meaningful? |
| ---------- | ------------- | --------- | ----------- |
| AI         | No            | No        | Yes         |
| GA         | No            | Yes       | Yes         |
| Clustering | Yes           | Yes       | No          |

These cases suffice to demonstrate that statistical software can not be
defined or assessed in terms of any notions of absolute reproducibility;
of being unbiased; or of being able to generate meaningful results. The
question is how such issues might best be approached in defining and
assessing statistical software? Perhaps the simplest approach would be
to have these as notionally defined categories of statistical software,
with due and encompassing acknowledgement that software within any of
these categories may suffer or manifest the nominated shortcomings. The
latter case of clustering algorithms nevertheless illustrates the
difficulties such a categorisation may face. As mentioned, the term
“clustering algorithms” was intended only as a synecdoche for a
general, encompassing category of software *potentially* incapable of
generating statistically meaningful results. Many other algorithms,
implementations, and pieces of software could also fit within this
general category, many of which may also fit within the other two
categories considered here.

An AI algorithm capable of categorising some set of input objects to an
accuracy determined by some selected set of human assessors can only be
deemed to yield meaningful output to the extent that the judgements of
the selected set of assessors may be adjudged meaningful by some
general, and generally representative, portion of (some) society. An
element of subjectivity may be accordingly unavoidable in assessing
statistical software, suggesting perhaps a need to have developers
attempt to explicate potential areas or causes of subjectivity.

A tentative suggestion at this early point of development would be to
reach a binary decision of whether to categorise software along the
lines of the row names in the above table, and associate a list of
potential problems or shortcomings with each of the given categories; or
to categorise software directly according to the column names of
potential problems or shortcomings, regardless of the explicit category
to which it may be judged to belong. These potential problems are given
further, explicit consideration within the following sections.

# 3\. Software Reviews, Testing and Validation

There is a wealth of literature on software reviews, software
verification and validation, and software testing, either as independent
topics, of considered as aspects of a unified whole. Of particular use
in developing the following have been the reference works of Mili (2015)
and Ammann and Offutt (2017). All of the following topics and concepts
are inextricably entwined, as can be seen in the associated [network
diagram presented
here](https://mpadge.github.io/statistical-software/testing-and-validation/).
The following sub-sections roughly correspond to the individual groups
within that diagram.

## 3.1 Verification and Validation

The topics of Software Verification and Validation have been granted
very extensive consideration. One work of particular note is the
comprehensive reference of Vogel (2011). The concepts of verification
and validation may often have only peripheral validity of open source
software in general, and to much of the software curated by rOpenSci,
yet these concepts are nevertheless of direct relevance within
particular fields, very notably software for pharmacological research.
Within these field, these concepts are being concurrently investigated
by the [“R Validation Hub”](https://www.pharmar.org/), which is,

> a cross-industry initiative whose mission is to enable the use of R by
> the bio-pharmaceutical industry in a regulatory setting, where the
> output may be used in submissions to regulatory agencies.

One regulatory agency of particular focus in that context is the United
States Food and Drug Administration (FDA), who publish their own
[“General Principles of Software Validation”
(2002)](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/general-principles-software-validation)
(for Devices and adiological Health 2019). Much validation and
verification work has also been directed towards the R language itself,
resulting in the R Foundation’s document on “Regulatory Compliance and
Validation Issues” (The R Foundation for Statistical Computing 2018).
Such work is considered beyond the scope of rOpenSci’s Statistical
Software project, which will retain a focus on R *packages* rather than
the language as a whole. Some of the procedures and protocols developed
for such endeavours may nevertheless be of relevance and interest for
this project. Of more direct relevance is the current primary output of
the R Validation Hub, in the form of a [White
Paper](https://github.com/pharmaR/white_paper), the content of which
overlaps many of the concepts presented and discussed here.

Of critical importance in the present context is the fact that almost
all work on software verification and validation has been focussed on
closed-source commercial software, with one of the only works of note to
date on verification and validation of open-source software being a
conference paper from 2012 (Stokes 2012). That paper is nevertheless
largely discursive in nature, and largely rests on unproven assumptions
that open-source software *may* pose greater probabilities of risk due
to such factors as novelty, poor software quality, poor documentation,
difficulties in controlling the production environment, and
compatibility issues with unverified infrastructure, and a decreased
risk detectability. All of this issues may equally plague closed-source
software. The merit of that work appears to lie in its consideration of
the importance of community for open-source software, and the importance
for the purposes of verification and validation of *assessing* such
community. They consider the following questions:

>   - Is there a formal community supporting the software or is it just
>     a loose collection of individuals?
>   - Does the community have any formal rules or charter that provide a
>     degree of assurance with respect to support for the software?
>   - How mature is the software? How likely is it that the open source
>     community will remain interested in the development of the
>     software once the immediate development activities are complete?
>   - What level of documentation is available within the community? How
>     up-to-date is the documentation compared to the software?
>   - How does the community respond to identified software bugs? Are
>     these fixed in a timely manner and are the fixes reliable?
>   - What level of testing is undertaken by the community? Is this
>     documented and can it be relied upon in lieu of testing by the
>     regulated company?
>   - What level of involvement are we willing to play in the community?
>     Will we only leverage the software outputs, or actively support
>     the development?

## 3.2 Software Review

The primary emphasis of almost all prior work on software review is the
need for review to be *external and independent* in order to ensure
objectivity and impartiality. While is may be tritely assumed that
rOpenSci’s system goes a great way to ensuring such externality and
independence, it is important to note that current review practices only
partially overlap conventional or traditional domains of “software
review”. In particular, software review is traditionally very directly
focussed on explicit review of code, and less so on broader or more
general aspects of functionality and usage. All of these aspects are so
intimately entwined ([click here to view interactive network
diagram](https://mpadge.github.io/statistical-software/testing-and-validation/)),
that such entwinement should rightly be interpreted to reflect a need to
clearly clarify the scope and design of review itself.

It should also be noted in relation to the interactive network diagram
that the centrality of review within that network likely reflects a
pervasive difficulty within the extant literature in defining the scope
of review. This difficulty in definition translates into the concept of
review being tentatively related to many other, more diverse yet readily
defined aspects (such as testing). Whether or not the centrality of
review is an artefact, the following two important aspects emerge as
subsets, and direct repeats, of the more general questions considered
under the general topic of “Review” at the outset:

1.  At what point(s) during the development of software should review
    start and end?
2.  Should review be a one-off phenomenon, or should there be ongoing
    engagement?

## 3.3 Software Metrics

There are uncountably many software metrics, many of which are equally
applicable to both closed- and open-source software. These can be
broadly categorised into the following three sub-classes.

### 3.3a Formal Computer Science Metrics

There are many formal computer science software metrics, for which one
particularly useful reference is Myers, Badgett, and Sandler (2012).
This book provides a solid semi-theoretical basis for graph-based
metrics of software performance, testing, and evaluation. One
particularly useful insight they provide is a formula defining a
required number of users to achieve an expected rate of fault discovery.
This could be very usefully and directly translated into formal
procedures for verification and validation of open-source software.

The book discusses many other formal computer science metrics such as
cyclomatic complexity and code volume. Importantly, almost all formal
computer science metrics for code quality are *graph based*, yet there
is no current software within R capable of providing such analyses.
(Current metrics of cyclomatic complexity are based on sub-graphs within
single functions only, and are not based on analyses of entire package
graphs.) While graph-based metrics may be criticised, the inability of
any current system to provide a comprehensive graph-based insight into
package structure and functionality can not be ignored.

Of particular use in devising graph-based analyses of R packages is
almost certainly the [`pkgapi`
package](https://github.com/r-lib/pkgapi), which relies on the
relatively recently re-designed `R::utils` function `getParseData`.

### 3.3b Documentation Metrics

Documentation metrics are generally very straightforward to assess, and
may consist of one of more of the following aspects:

1.  Total numbers of line of documentation
2.  Proportion of documentation to code lines
3.  Proportion of exported functions that are documented
4.  Extended documentation in the form of vignettes
5.  Documented examples for exported functions

### 3.3c Meta Metrics

Meta metrics include aspects such as development histories of packages,
usage statistics, and empirical reputation metrics of software
developers. The [`riskmetric`
package](https://github.com/pharmar/riskmetric) developed as part of the
[PharmaR initiative](https://pharmar.org) is currently primarily
focussed on meta metrics, including the following (in arbitrary order)

1.  Size of code base
2.  Release rate
3.  Website availability
4.  Version control availability
5.  Metrics of response to bug tracker issues
6.  Presence of a package maintainer
7.  Numbers of active contributors
8.  Suitability of software license
9.  Number of package downloads, and download history
10. Metric of “community enthusiasm”
11. Time for develop(s) to respond to bug reports
12. Time for develop(s) to respond to pull requests
13. Metric of community engagement in issues
14. Availability of a public code repository
15. Code coverage
16. Code coverage assessed by function examples only
17. Availability of examples
18. Documentation

## 3.4 Testing

Current R testing is arguably very focussed on “unit testing”, largely
in ignorance of the maxim that (Vogel 2011),

> A validation program that depends on testing alone for a defect-free
> device is depending on perfection in testing.

There are entire taxonomies of, and systematic approaches to, testing,
for which Mili (2015) provides a notably comprehensive overview.

### 3.4a Types of Tests

It ought to be particularly emphasised that unit testing is very
generally considered an activity conducted by developers and relevant to
developers (only). It seems regrettably necessary to note that this
practice gained its nomenclature to indicate nothing more than testing
software at the *smallest possible scale* of “fundamental” units,
regardless of any inter-dependence between those units. The testing of
such inter-dependence between units is accordingly referred to as
“integration testing”, while testing of explicit functions within a
piece of code is referred to “functional testing.” These categories can
of course not generally be clearly defined, but the distinction between
lowest level “unit testing” and any form of higher level (functional or
integration) testing is nevertheless useful. The structure of R packages
makes for a particularly clear distinction between these two:

1.  Unit Testing tests all functions and functionality *internal* to a
    package
2.  Integration Testing tests all *exported* functions of a package—and
    only those functions.

(Along with a potential corollary that “functional testing” is, or is
agreed to be, largely meaningless for R packages.) Those consideration
alone highlight the importance of explicitly determining whether tests
of and within an R package should best focus on testing *exported*
functions (only), or whether they should focus on testing internal
(non-exported) functions?

There are many other taxonomies and types of tests, with most texts on
the subject emphasising the importance of explicitly developing a schema
to guide the entire process of testing, including considerations of:

1.  The test environment
2.  The test data
3.  The test reporter
4.  Test termination conditions
5.  The test driver
6.  The test execution
7.  Analysis of test outcomes

It is worthwhile annotating and repeating these components within the
context of current practice for R packages:

1.  The test environment — generally, and justifiably, not considered
    relevant
2.  The test data — entirely ad hoc, and left to developer
3.  The test reporter — commonly `testthat` output parsed by `R CMD
    check`
4.  Test termination conditions — generally not considered relevant?
5.  The test driver — very generally `testthat`
6.  The test execution — always `R CMD check`, but other options ought
    to be considered
7.  Analysis of test outcomes

Testing can also have different goals, such as:

1.  Finding and removing faults
2.  Proving absence of faults
3.  Estimating frequencies of failure
4.  Ensuring infrequency of failure
5.  Estimating fault densities

There is arguably no current practice within the development of R
packages that considers testing to have any particular defined goal, let
alone consideration of the consequences of potential differences between
these goals. The entire domain of testing within R packages only very
cursorily reflects current approaches to, practices and theories of,
testing within modern computer science texts.

### 3.4b Content of Tests

Tests should be designed to explicitly measure one of more of the above
aspects of software faults and failures (generally presence/absence or
frequencies). The structure of `R CMD check` has arguably enforced on
the R community a practice of testing as confirming the absence of
faults. This is of course never possible, and is emphasised in most
texts as extremely undesirable, because it does little more than confirm
the limitation of implemented tests.

Contents of tests depend directly on the intended types of tests. In
particular, Mili (2015) distinguish “concrete”, “symbolic”, and
“stochastic” tests. The former of these arguably describes all current
R practices: testing concrete inputs against concretely-specified
expected outputs. In contrast, symbolic tests are exceedingly difficult,
and examine and test the “impact of execution on symbolic data”, while
“stochastic” testing aims to statistically summarise the expected
output of full symbolic tests, obviating the necessity of implementing
full symbolic tests, as explored further in the following sub-section.

### 3.4c Property-Based Testing

Parallel to works on formal taxonomies of testing are systems for
specifying and testing *expectations* of software inputs and outputs.
There appears to be no current consensus on vocabulary for such, but
domains in which expectations have been considered include property
testing, fuzzing, and particularly the above-mentioned domain of
stochastic testing. Fuzzing encapsulates the underlying concept of
examining software outputs in response to stochastically generated
inputs. Fuzzing was, and continues to be, developed in a largely
independent domain of software *security*, where it has proven to be
particularly useful in detecting software vulnerabilities. Although this
domain of application may not be directly relevant to much of R package
development, the underlying tools and methodologies may nevertheless be
relevant. In particular, many of the most widely used fuzzing tools
employ what are referred to as “coverage-based fuzzing” as a form of
effectively black-box testing. A program is compiled with symbolic links
to code entities, and the “fuzzer” modifies its input to attempt to
maximise the exploration space traced between input and output.

As explained, fuzzing has been largely confined to its own domain of
software security and vulnerability, yet there are strong and direct
parallels to incipient domains of “property-based testing” (credit for
that term to David MacIver, lead developer of the python [`hypothesis`
software](https://github.com/HypothesisWorks/hypothesis) for doing
exactly that). Property-based testing replaces standard concrete
testing—what might be term “instantiation testing” because what is
tested are concrete instantiations of particular inputs and outputs—with
generic *properties*. The canonical example is replacing an
instantiation test with a univariate input such as,

``` r
output <- my_function(input = 31)
expect(output == <expected_single_output>)
```

with a property-based equivalent,

``` r
output <- my_function(input = rnorm(1, mean = 0, sd = 1))
expect(output == <expected_distributional_output>)
```

or more powerfully,

``` r
output <- my_function(input = norm_dist)
expect(output == <expected_distributional_output>)
```

where `norm_dist` is ascribed some set of defined properties, as are the
instances of `<expected_distributional_output>`. These properties then
form the basis of the “property-based testing” of `my_function`, and may
include, for example, the extent to which one or both of input and
output might deviate from stated or expected distributional forms. There
have been previous attempts to devise such systems for R packages,
perhaps most notably the [`fuzzr`
package](https://github.com/mdlincoln/fuzzr), and the [`quickcheck`
package](https://github.com/RevolutionAnalytics/quickcheck) by
RevolutionAnalytics, both of which appear to have long been abandoned.
The software which appears to best encapsulate current best practices in
this regard in any language appears to be the above-mentioned
[`hypothesis` software](https://github.com/HypothesisWorks/hypothesis)
for python. This software requires explicit specifications of tests
using its own internal grammar of assumptions or pre-conditions, defined
by a series of `@given` statements, a definition of what is being
tested, and a statement of expected output (generally via one or more
`@assert` statements). This is a far more powerful framework than
anything currently considered or possible within R (notwithstanding the
two packages mentioned above).

### 3.4d Testing Grammar

As mentioned, testing is R is currently very largely defined by the
`testthat` package, which offers its own grammar of expectations (via
`expect_that`-type statements). These are directly equivalent to the
`@assert` statement of `hypothesis`, yet absent any ability to define
`@given` statements, and therefore entirely restricted to tests of
concrete instantiations only. The actual grammar of `hypothesis` is
arguably only slightly more extensible in permitting such `@given`
statements of pre-conditions or assumptions, yet these render the
current testing grammar of `hypothesis` enormously more powerful than
`testthat`, through being able to test general properties of inputs,
rather than concrete instantiations. The ultimate aim of `hypothesis`
nevertheless appears to be to develop a far more generic, and more
powerful, grammar for specifying both tests and more general behavioural
expectations of software.

The current “best practices” framework for grammars of expectation
appears to be the [`gherkin`
language](https://cucumber.io/docs/gherkin/) developed for the
[`cucumber` system for “Behavior-Driven
Development”](https://cucumber.io). This grammar enables plain
English-style statements to be made both for test expectations and for
pre-conditions or assumptions. Importantly, these are embedded within
statements of “Scenarios”, which means that the crucial component of
[`gherkin`](https://cucumber.io/docs/gherkin/)-type systems for
open-source software is that precisely the same grammar is shared by all
of:

1.  Software tests;
2.  Software specifications;
3.  Software bug reports; and
4.  Software feature requests.

While the development of such a system may be judged to lie well beyond
the scope of the current rOpenSci project, consideration of such may
nevertheless be warranted, particularly if pursued in conjunction with
concurrent developments in python. It ought to especially be noted that
the `@given` statements of both `hypothesis` and `gherkin/cucumber` very
frequently translate to expectation of *statistical properties*, and are
thus likely to be of particularly direct relevance to statistical
software. We now consider further arguments for serious consideration of
such systems within the context of statistical software, with particular
reference to the foregoing considerations of types of statistical
software.

### 3.5e Property-Based Testing and Statistical Software

Implementing property-based testing within or for R package may be
judged too ambitious within the scope of the present project, yet this
sub-section presents a brief argument for serious consideration. We
consider by way of example, with reference to the above categories of
statistical software, considered in this context in terms of the column
names of the preceding table, defining whether software generates
results that are (i) Reproducible? (ii) Unbiased? and (iii) Meaningful?
Consider, for example, reproducibility which, among other important
aspects, should only ever be defined (in the best possible
circumstances) within some degree of machine precision, and so can in
this trite yet strict sense only rightly be considered a phenomenon of
distribution rather than instantiation, Testing reproducibility thus
requires some form of distributional–or *property-based*–testing. More
generally, many of the problems encapsulated in the foregoing
considerations of “difficult” categories of statistical software could
be effectively addressed by specifying software capabilities in
distributional or property-based terms.

Continuing with the above example, software that fails to generate
“reproducible” results according to some “standard” definition of that
concept could nevertheless be specified to transform a given
distributional input into an expected distributional output, with that
output encapsulating the distributional uncertainty associated with some
explicitly acknowledged degree of irreproducibility. Similarly, software
that (potentially) generates biased results could readily and explicitly
acknowledge such via an appropriate property-based grammar of testing
along such lines as,

``` r
given(my_input1 = <our_training_data>)
output1 <- my_function(input = my_input1)
expect(output1 == <expected_distributional_output1>)
given(my_input2 = <different_training_data>)
output2 <- my_function(input = my_input2)
expect(output2 == <expected_distributional_output2>)
expect(<expected_distributional_output1> != <expected_distributional_output2>)
```

Specification of expected distributional differences in output would
then amount to an explicit specification of expected bias.

This brief sub-section hopefully suffices to illustrate how the
unavoidable problems identified above in regard to classifying types of
statistical software might be very effectively overcome through
implementation of an appropriate grammar for property-based testing, and
that doing so could go a long way towards obviating much need to
delineate and categorise either different types of statistical software,
or different types of expected divergence from generally expected
behaviour of statistical software.

# 4\. Software Design

Like testing, software design has been granted extensive prior
consideration, and a notably useful reference is again Mili (2015), who
identify the following three primary attributes, and sub-components
thereof (all shown within the [interactive network
diagram](https://mpadge.github.io/statistical-software/testing-and-validation/)):

1.  Functional Attributes
      - Correctness
      - Robustness
2.  Useability Attributes
      - Ease of Use
      - Ease of Learning
      - Customizability
      - Calibrability
      - Interoperability
3.  Structural Attributes
      - Design Integrity
      - Modularity
      - Testability
      - Adaptability

rOpenSci’s guide on [package development, maintenance, and peer
review](https://devguide.ropensci.org/) provides arguably one of the
most prominent guides on the design of R packages, primarily with its
first chapter. One of the few other notable examples of guides to design
principles of R packages is the [tidyverse design
guide](https://principles.tidyverse.org/). It is nevertheless notable
that both of these primarily focus on what might be considered more
technical aspects of package development at the expense of the more
general concepts listed above, particularly those listed under
“Useability Attributes”.

## 4.1 Software Lifecycles

A key determinant and constraint of software design arises through it
being explicitly embedded within a defined “software lifecycle”. There
has been a great deal written about software lifecycles, and a large
variety of models proposed to describe or define “software lifecycles”
(Mohammed, Munassar, and Govardhan 2010; Kumar, Mishra, and Mehta 2016).
All of these models are unavoidably generic, and most of them—one might
justifiably assert, “merely”—serve to enable a visual diagram that
connects various components deemed to be important to consider
throughout an ongoing process of software development and improvement.
None of these proposed models ought be considered any more or less worth
of consideration than any other, and with that no particular model ought
be considered worthy of any particular, explicit consideration. What
nevertheless unites all such models is their universal basis in a
conceptualisation of software development as an inherently *commercial*
activity, and as such a great deal of most such models is arguably not
directly applicable to notions of software lifecycles which might be
typical of open source software (although see Spencer et al. 2015 for an
example). A few general comments are nevertheless instructive, including
the following:

> The software life cycle contains software engineering tasks and
> documentation necessary to support the software validation effort. In
> addition, the software life cycle contains specific verification and
> validation tasks that are appropriate for the intended use of the
> software (for Devices and adiological Health (2019)).

Vogel (2011) further provides the following list of components of a
software lifecycle, done while importantly emphasising that one ought
never presume the universal applicability of a single model of a
software lifecycle:

  - Quality Planning
  - System Requirements Definition
  - Detailed Software Requirements Specification
  - Software Design Specification
  - Construction or Coding
  - Testing
  - Installation
  - Operation and Support
  - Maintenance
  - Retirement

## 4.2 Software Testing Lifecycles

Mili (2015) discusses the potentially important concept of a Software
*Testing* Lifecycle, although the discussion points themselves are quite
generic.

## 4.3 Lifecycles of Open Source Software

Important questions:

  - *Is there a “lifecycle” for open source software? Or is it just a
    manifestion of an indefinable and dynamic aspect of a sn indefinable
    community?*
  - *Can the developmental processes of open source software be
    characterised to any sufficient degree of accuracy by a necessarily
    simplistic “model” of a development “lifecycle”?*
  - *In the apparent absence of any applicable or useful model for the
    lifecycle of open source software, would it be useful for the
    project to explicitly develop and specify one or more such models?*

With these three questions held in mind, the following sub-sections
attempt to exemplify what such a model might look like, and therewith to
explore the potential utility to be gained by developing, implementing,
and referring to such a model.

### 4.3a What might a model of an Open Source Software Lifecycle look like?

Open source software may often be initially conceived of and designed to
meet or fulfil some specific goal of one or more (initial) primary
developers, yet its ongoing development is frequently and strongly
influenced by open and ongoing community engagement with the software.
Such engagement is inherently unpredictable, and arguably must lead to
developmental trajectories being less predictable than for equivalent,
closed source software, and therefore less amenable to being represented
in terms of simplified models. For the purposes of understanding the
potential form of a model for the lifecycle of open source software, it
nevertheless seems reasonable to initially distinguish between the
following three primary developmental phases:

**1. Initial Conception and “Internal” Development** This is perhaps the
single stage in the development of open source software which has
sufficiently strong parallels to models of general (closed source)
software development for concepts to be broadly transferable and
applicable. In particular, this would be the phase defining such aspects
as Planning, Specification, and Design. The end of this stage might be
marked by an increase in community engagement with the ongoing
development of the software beyond some minimally sufficient degree,
such that the ongoing form of the software and its developmental process
becomes significantly affected by influences external to the primary
developer(s).

**2. Ongoing, Open Development** This phase can be less well described
by conventional models of software lifecycles, because the ongoing
engagement of a truly open community must lead to some degree of
uncontrollability in the process of ongoing development. Beyond central,
technical questions defining development platforms, version control
systems, update and release frequencies and strategies, and platforms
for community engagement and contribution, equally important
“meta-questions” which must likely be confronted during this phase
include:

1.  The extent to which control over the developmental trajectory of
    software can, will, or might best be granted to non-primary
    (“community”) developers;
2.  The *desired* extent of community engagement in development, and
    whether it is desired that such engagement increase over time? (And
    potentially: if so, how?)
3.  The extent to which development might be defined by bug reports,
    feature requests, and similar input which nevertheless may or will
    require explicit action of primary developers, versus developmemnt
    more determined by direct community code contributions (such as pull
    requests).

Many similar questions could be added to that list, but these are
intended to be interpreted as illustrative of the kinds of decisions
that could be, and likely often are, made and which directly determine
the developmental trajectories of open source software, and yet which
are likely often made only implicitly, or absent explicit awareness or
reflection. The intent of the present section is to explore the extent
to which an explicit model of an open source software lifecycle might be
useful, for which we will return to these questions immediately below,
keeping in mind that their primary function here in intended to be
*exemplary*. In doing so, it may nevertheless be instructive to consider
the possibility of two distinct (sub-)phases within this second, general
phase:

1.  Active, open development with significant changes in structure and
    function; potentially leading to:
2.  Stability in structure and function, with subsequent development
    primarily responding or being directed to finding and fixing faults,
    increasing software stability or performance, or other periheral
    functional embellishments.

Those two phases may, of course, often cycle in sequence, with phases of
relative stability followed by additional, subsequent phases of active
development.

**3. Decline to Senescence, Abandonment, Integration, and other possible
end fates** (where Integration is intended to imply that the software
becomes integrated as a part of the ongoing development of some other,
effectively independent piece of software, thereby handing over
responsibility for subsequent development to a different set of
developers.) This phase might broadly typify a terminal phase for both
open and closed source software, yet the dynamics likely differ, because
open source software can approach and traverse this phase through three
categorically different processes of disengagement of (primary)
developers, disengagement of users, or disengagement of non-primary
developments. Closed-source software can arguably only approach and
traverse this phase through intentional decisions on the part of primary
developers in response to either user disengagement, or decisions
otherwise not directly related to the software itself. The entrance
point to this phase for open-source software might thus be distinguished
between the three categories of:

1.  Disengagement of primary developers;
2.  Disengagement of non-primary developes; and/or
3.  Disengagement of users

One distinct possibility might be that primary developers disengage to
some significant degree from ongoing development due to development
having reached a stable developmental state as described immediately
above. Thus, although such a state may be desirable from a developer
perspective, it may also represent a danger in that decreased need for
ongoing active engagement may translate into disengagement sufficient
for software to approach a state of senescence. Whether software
development approaches or enters a terminal phase through this or other
processes, negotiating and planning for traversal of such a phase likely
requires addressing the following kinds of questions:

1.  What might cause such disengagement?
2.  What might be the potential consequences of such disengagement?
3.  How might the primary developer(s) respond to such disengagement?

Each of these questions could potentially be anticipated during the
first or second preceding phases, perhaps usefully embedded within a
risk-based assessment whereby each question could be addressed in terms
of likelihood and consequence, with risk “scores” quantified as the
product of likelihood times consequence. The remainder of this
sub-sections illustrates what a potential risk-based model of an open
source software lifecycle might look like.

The risk-based framework is developed by assigning a risk to each
component, in order to elucidate and emphasise different risks presented
by and for different developmental phases. Each phase and sub-phase is
also associated with an estimated duration, enabling an overall estimate
of software lifespan.

| Phase | Description                                                                   | Duration (years) | Cumulative Development Time (years) |
| ----- | ----------------------------------------------------------------------------- | ---------------- | ----------------------------------- |
| 1     | Initial Conception and “Internal” Development                                 | 1                | 1                                   |
| 2a    | Phase of active, open development                                             | 1                | 2                                   |
| 2b    | Phase of initial stability and expansion in use                               | 1                | 3                                   |
| 2c    | Secondary phase on active, open development and consolidation                 | 1                | 4                                   |
| 2d    | Secondary phase of stability                                                  | 2                | 6                                   |
| 3     | Decline to Senescence, Abandonment, Integration, and other possible end fates | 1                | 7                                   |

The following table elucidates a number of potential risks associated
with each phase, and quantifies their associated likelihoods and
consequences in qualitative terms of either “low”, “medium”, or “high”.

| Phase | Year Number | Risk Factor                                               | Likelihood | Consequence |
| ----- | ----------- | --------------------------------------------------------- | ---------- | ----------- |
| 1     | 1           | Development too slow                                      | medium     | low         |
| 1     | 1           | Development misdirected; software ineffective             | low        | high        |
| 1     | 1           | Development misdirected; software inefficient             | high       | low         |
| 1     | 1           | Insufficient developer expertise                          | medium     | high        |
| 1     | 1           | Competing software unexpectedly developed                 | low        | high        |
| 2a    | 2           | Insufficient community engagement                         | high       | medium      |
| 2a    | 2           | Unexpectedly high community engagement                    | low        | low         |
| 2a    | 2           | Community needs & desires differ from developers’ visions | medium     | low         |
| 2a    | 2           | Competing software unexpectedly developed                 | low        | high        |
| 2b    | 3           | Users lose interest                                       | medium     | low         |
| 2b    | 3           | Developers lose interest                                  | low        | high        |
| 2b    | 3           | Developers no longer able to devote time to project       | medium     | high        |
| 2b    | 3           | Competing software unexpectedly developed                 | medium     | high        |
| 2c    | 4           | Insufficient ideas from developers / community            | high       | low         |
| 2d    | 6           | Users lose interest                                       | high       | medium      |
| 2d    | 6           | Developers lose interest                                  | high       | medium      |
| 2d    | 6           | Developers no longer able to devote time to project       | medium     | medium      |
| 2d    | 6           | Competing software unexpectedly developed                 | high       | high        |
| 3     | 7           | Users lose interest                                       | high       | high        |
| 3     | 7           | Develpers lose interest                                   | high       | high        |
| 3     | 7           | Developers no longer able to devote time to project       | medium     | high        |
| 3     | 7           | Competing software unexpectedly developed                 | high       | low         |

Many more factors could be added to this list, but that table suffices
to illustrate how the construction of this software lifecycle in terms
of distinct phases of defined durations has allowed quite concrete
identification of risk factors associated with each phase. In
particular, note that if the qualitative values of “low”, “medium”, and
“high”, are translated into respective numeric values of 1, 2, and 3,
then the overall risk across the anticipated lifespan of this
hypothetical software can be immediately quantified and visualised, as
shown in the following graph.

<img src="figures/lifespan-risk-1.png" width="100%" />

That graph usefully reveals the greatest risk to arise in the fifth and
sixth years of development, prior to anticipated terminal phase in year
seven. (This terminal phase is of course associated with a high overall
risk, because it is the phase in which the software is anticipated to be
abandoned.) The fifth phase of development encompassing the fifth and
sixth years was projected to be the second phase of stable
development—the phase during which the developers might otherwise be
able to “sit back and enjoy” widespread use of and acclaim for their
software with relatively little effort required on their part. This
graph might therefore be considered very useful in highlighting the need
to strategically anticipate and plan to mitigate the risks associated
with this notionally “easy” phase.

Prior to approaching a stable state in the sixth year, the graph
indicates the phase of lowest risk to be during the fourth year, and so
also usefully highlights the need to ensure the comparatively elevated
risks associated with the first three phases are successfully managed to
ensure the greatest chance of transitioning into this fourth phase. This
highly simplified demonstration of an explicit lifecycle model thus
demonstrates one immediate utility in enabling the identification of
distinct risks, thereby naturally enabling and empowering effective
action to be taken against such risks.

This risk-based framework is intended to demonstrate how such a concrete
reference for the distinct phases of a software lifecycle model might
allow for effective analysis, planning, anticipation, and amelioration
of potential negative effects on the success of a software project.
There are of course many other possible models of a software lifecycle,
as well as many other frameworks which might be considered, such as
quantifying expected or desired numbers of users or active contributors,
Regardless of how a lifecycle or developmental trajectory might be
analysed and quantified, this model reveals the immediate utility of
explicitly considering and identifying distinct phases of development,
in order to examine each in terms of risk (or whatever other metrics
might be deemed appropriate for a particular project), and ultimately to
enable an explicit and quantitative analysis of the kind presented in
the above graph.

### 4.3b How might a model of an Open Source Software Lifecycle help this and other projects?

We note at the outset that answering that question likely necessitates
some kind of answer to the more general question of how models of
software lifecycles in general have helped software development in
general. We simultaneously acknowledge that it is not likely possible to
answer that question. Having done so, we nevertheless attempt within the
present sub-section to address the following two, related questions:

**1. To what extent might a lifecycle model of open source software
actually aid the development of software during any one, or indeed all,
of these stages?** The preceding sub-section has demonstrated the ease
with which a software lifecycle model might enable the identification
and assessment of risks associated with each phase of development. The
identification of risk is, as always, the first necessary step required
to effectively anticipate, ameliorate, and reduce risks associated with
development, and thus a lifecycle model could clearly be used to reduce
risks associated with and during any identified developmental phases. In
such cases, the explicit identification of lifecycle phases simplifies
the task of identifying associated risks, through constraining those
risks to finer-scale and thus conceptual simpler developmental phases.
The question then naturally arises as to what other kinds of frameworks
might be usefully developed and applied?

**2. To what extent might a lifecycle model of open source software aid
the process of peer-review?** This question is, at least superficially,
relatively easy to address. A model can very likely aid the
identification of effective entry and exit points for the peer review
process. (Such a statement is of course itself not free of tautology:
any such model which *only* serves such a purpose can not differ
substantially from direct identification of entry and exit points; we
ignore such potential tautology here under the assumption that our
models also serve additional purposes.) The obviously most appropriate
phase for software review would be the transition between the first and
second phase, from the end of “internal” development to the second phase
of open community engagement in both use and further development. This
also seems to generally coincide with the majority of rOpenSci packages,
particularly following the current recommendation that packages not only
CRAN only be submitted following successful review and acceptance by
rOpenSci.

Developers might reasonably be required to formalise a lifecycle model
for their software for the purposes of review. Doing to would very
likely only aid developers by providing a concrete structure within
which they might express and codify visions for future package
development (with associated benefit likely being greater the earlier in
the development process a lifecycle model is developed). The above table
and graph demonstrate the usefulness of doing so, even when such visions
can only be expressed in broad, generic terms, and only ultimately
considered within the single framework of risk. It would seem fair to
assume that being mandated to develop such an explicit model would
generally be of some finite benefit both to developers and to the
software itself.

Perhaps more importantly, such a model would also aid the task of
peer-review. The software lifecycle model itself, along with associated
risks, could itself become subject to scrutiny by reviewers. At what
might arguably be considered one level of generalisation above that,
review might also serve a useful function during any of the subsequent
phases. One additional level of generalisation or abstraction beyond
that might then involve the identification of some “utility of review”
to each phase of development, as a simple, additional column on the
above risk table. This suggests the following three classes of
possibilities for incorporating lifecycle models within the peer review
process:

1.  Require a software lifecycle model to be included within a package,
    and itself to be subject to review, with review generally presumed
    to occur between some equivalent of the first and second of the
    above phases (absent explicit, alternative specification);
2.  Require a lifecycle model to also indicate perceived or anticipated
    utility of review for each phase, with the entire review process
    adapting to and extending across any and all nominated phases.

Entry points in both cases might be the same (and likely most usefully
occur towards the end of the first, initial phase of “internal”
development), yet the end points would then differ, with the second
option extending the end point across much of the entire software
lifecycle (and potentially also having several concrete or recurring
exit and re-entry points).

(It must also be noted that while the latter might be of considerable
benefit, using the same reviewers throughout would also progressively
increase their familiarity both with the code itself, and with its
developmental history, rendering them increasing less capable of
offering truly “external” review. This process would itself then
introduce and entail an additional risk of decreasing the required
degree of “external” objectivity on the part of reviewers. It
nevertheless seems very likely that any such risk would have to be
ignored, as finding new reviewers for each and every review phase would
place an excessively onerous burden on each of these reviewers,
particularly through them having to familiarise themselves not only with
unfamiliar code, but with all prior reviews and responses to such, as
well as on editors responsible for finding greater numbers of reviewers
for each package. For now, we merely acknowledge the likely presence and
unavailability of such an effect.)

We close this section by simply noting that the current rOpenSci
practice of effectively having entry and exit points for peer-review
between the first and second of the above phases places that process in
the middle of the relatively low risk phase of overall development of
the above figure. Although that figure was only intended to be
illustrative, and although the data behind it were not intended to be
anything other than exemplary of the kinds of risk factors which might
be associated with each hypothetical developmental phase, these phases
and associated risks might nevertheless be considered sufficiently
generic as to be of some general applicability. This being the case, the
figure graphically illustrates that the current review process ceases
prior to entering what might actually be the highest risk phase of
software development. That alone may be interpreted to argue strongly
for the second of the above options rather than the first: that is, for
a review process which includes lifecycle models which (may) themselves
identify multiple phases, or multiple entry and exit points, for review.

# 5\. Community

This section considers aspects related to community engagement,
equality, reach, fairness, and representativeness. It considers
community in terms of the threee distinct aspects of:

1.  Communities of users and contributors to packages;
2.  Communities of developers; and
3.  Communities of reviewers for software submissions.

The first communities coalesce around individual packages; the second
around rOpenSci itself and its general package ecosystem, and the third
may be drawn from the second, yet will likely require additional, active
cultivation. Prior to directly addressing these communities, we begin
this section by considering the kinds of metrics which may be able to be
empirically derived and used to quantify users, contributors,
contributions, packages, and potential reviewers.

## 5.1 Metrics of Community Construction and Engagement

The project under consideration here arguably attempts to improve upon
an historical, and historically documented, process leading to the
construction of the current and ongoing community surround the rOpenSci
peer review process. Much might accordingly be gained by examining the
historical developmental dynamics of rOpenSci, both of individual
packages, and of more general communities surrounding the general
peer-review process and entity of rOpenSci itself. An example of the
kind of analysis possible via git commit histories as uploaded to github
is [our analysis of contributions by non-primary authors to rOpenSci
packages](https://github.com/mpadge/ros-pkg-authors). Such analyses can
readily be adapted and extended to a variety of other modes and
measures.

### 5.1a Metrics of package use and contributions

The single generally used proxy for usage of R packages is the number of
downloads obtained from RStudio’s CRAN mirror, and provided by the
cranlogs service. Although is it possible to obtain additional numbers
of downloads from github itself, the cranlogs values are likely
sufficient for most analytic purposes. Many metrics of contributions
could be derived along the lines of the code contained in the repository
linked to above, including:

  - Numbers and/or proportions of non-primary contributors
  - Numbers and/or proportions of issues opened by non-primary
    contributors
  - Numbers of commits and/or lines of code by non-primary contributors
  - Numbers and/or proportions of pull requests by non-primary
    contributors
  - Numbers of visitors to github page and/or rOpenSci docs pages for
    each repository

### 5.1b Metrics of developer activity and/or engagement

Note that primary developers may be identified in a number of ways,
potentially yielding different results. Perhaps the least ambiguous way
is to identify primary develops as those listed in the `DESCRIPTION`
file with `role = "aut"`, *and who have also actively contributed lines
of code to a package*. (The latter is necessary because authors of any
internally bundled code should also be acknowledged as package authors,
yet such authors make no active contribution.) Other statistical
approaches may be also be derived and implemented as appropriate.

  - Numbers of lines of code
  - Temporal developments in numbers of lines of code (such as rates of
    change)
  - Proportion of lines of code in package under consideration compared
    with all lines of code committed by primary authors to all other
    repositories or packages
  - Numbers of issues (total numbers, total open issues, total closed
    issues, rates of issue turnover, times between opening and closing,
    and other measures)
  - Numbers of bug reports and metrics analgous to the above

### 5.1c Metrics for Potential or Actual Reviewers

The search for reviewers may well be aided by some kind of
quantification. It may also be of more general utility for the project,
and for rOpenSci in general, to quantify aspects of reviewer activity,
reviewer networks, or some of the other attributes now listed.

  - Number of repositories and/or packages developed by a reviewer
  - Contributions by a reviewer to other repositories/packages

It must be noted, however, that such metrics will likely lead to some
kind of ranking system for reviewers, and that such rankings may be
considered generally undesirable, particularly as rankings may
effectively exclude people new to coding, new to R, and/or new to the
concept of peer reviewed code. Such people may in fact be desirable,
particularly as the inclusion of ever more people can only increase the
diversity of reviewers, and hopefully with that, through each reviewer
connecting their own personal networks within those of rOpenSci,
increase the overall diversity of participants and software in general
within rOpenSci.

In lieu of potentially problematic metrics of the kind listed above, it
may also be useful to derive metrics to use in directly searching for
potential reviewers for a submission. Such metrics may include measures
of similarity or overlap between the code contained in the submission
and a reviewer’s own code. This may be achieved by, for example,
extracting all functional calls within a package, and within a
reviewer’s own code, and assessing similarity or overlap in functional
calls. More complex and potentially—although not
necessarily—comprehensive metrics could be derived by tracing networks
of functional calls both within a submission and reviewers’ code, and
correlating overall frequencies of functional calls. Similarity in
underlying functional call networks might usefully highlight reviewers
likely to be particularly capable of reviewing a given package. However
such an approach might be developed and employed, it would very likely
provide an effective way to overcome problems associated with the kinds
of coarse-scale individual metrics described above that likely and
inevitably lead to ranking (potential) reviewers.

## 5.2 Constructing and Maintaining a Community of Reviewers

One important question that extends directly from the preceding
considerations is how to *first* identify reviewers who might be subject
to the kinds of analyses proposed there? The most convenient way is
likely to be to compile a list of all individuals who are either members
of rOpenSci’s slack community; or who have contributed to or commented
upon any rOpenSci repository, whether through code, or opening or
commenting upon issues within github repositories. Such an approach may
nevertheless be less than ideal because these communities themselves may
be biased, or may not manifest some property such as diversity or global
coverage otherwise desired by rOpenSci. Searches might be extended
through considering all people who follow rOpenSci on twitter, or all
who have liked or retweeted an rOpenSci tweet.

Perhaps the greatest problem that may arise in pursuing any of these
suggestions might be the potential exclusion of people who do not
habitually upload code to public sites such as github or gitlab. It is
nevertheless the remit of rOpenSci to encourage and cultivate an *open
source* community, and such people might arguably be considered as
making less of a contribution to open source communities than those who
do regularly upload code, therefore justifying their potential
exclusion. It is likely nevertheless important to acknowledge any such
sources of bias or effective exclusion in developing or implementing any
system to aid searching for reviewers.

One potential way to overcome the kinds of limitations described
immediately above might be to identify an initial community pool, and
then contact via email or some other suitable forum all individuals
within that community and ask them to nominate additional people they
may know and who they might consider appropriate to review software.

Of course, for this and many other projects, there would ideally be
extant comparisons between various methods of passive and active
community construction and engagements, along with demonstrations of the
transferrability of (aspects of) approaches employed. The intractable
complexity of community dynamics renders such general comparisons either
impossible or meaningless, or both. It might nevertheless be possible to
consider and contrast sub-ecosystems surrounding specific (collections
of) R packages, and to examine dynamics of community growth and
engagement, along with potential metrics of passive or active
engagement. The present document will nevertheless not propose any
particular approach to doing so; it suffices here merely to note the
distinct possibility, particularly in order to emphasise the general
point that many assumptions or hypotheses regarding community dynamics
may be amenable to empirical enquiry, and that no particular models,
assumptions, or hypotheses of such ought to be necessarily accepted
absent empirical (or other external) support.

# 6\. References

<div id="refs" class="references hanging-indent">

<div id="ref-ammann_introduction_2017">

Ammann, Paul, and Jeff Offutt. 2017. *Introduction to Software Testing*.
Cambridge University Press.

</div>

<div id="ref-center_for_devices_and_radiological_health_general_2019">

for Devices, Center, and adiological Health. 2019. “General Principles
of Software Validation.” *U.S. Food and Drug Administration*.
<http://www.fda.gov/regulatory-information/search-fda-guidance-documents/general-principles-software-validation>.

</div>

<div id="ref-kumar_critical_2016">

Kumar, Subodh, N. K. Mishra, and Sarkar Sharan Mehta. 2016. “Critical
Analysis of Software Process Models.” *IJCA Proceedings on National
Conference on Advances in Computing Applications* NCACA 2016 (2): 12–14.
<https://www.ijcaonline.org/proceedings/ncaca2016/number2/26176-1043>.

</div>

<div id="ref-mili_software_2015">

Mili, Ali. 2015. *Software Testing: Concepts and Operations*.

</div>

<div id="ref-mohammed_comparison_2010">

Mohammed, Nabil, Ali Munassar, and A. Govardhan. 2010. “A Comparison
Between Five Models of Software Engineering.” *International Journal of
Computer Science* 7 (5).

</div>

<div id="ref-myers_art_2012">

Myers, Glenford J, Tom Badgett, and Corey Sandler. 2012. *The Art of
Software Testing*. Hoboken, NJ: Wiley.

</div>

<div id="ref-spencer_open-source_2015">

Spencer, J. S., N. S. Blunt, W. A. Vigor, Fionn D. Malone, W. M. C.
Foulkes, James J. Shepherd, and A. J. W. Thom. 2015. “Open-Source
Development Experiences in Scientific Software: The HANDE Quantum Monte
Carlo Project.” *Journal of Open Research Software* 3 (1): e9.
<https://doi.org/10.5334/jors.bw>.

</div>

<div id="ref-stokes_21_2012">

Stokes, David. 2012. “21 - Validation and Regulatory Compliance of
Free/Open Source Software.” In *Open Source Software in Life Science
Research*, edited by Lee Harland and Mark Forster, 481–504. Woodhead
Publishing Series in Biomedicine. Woodhead Publishing.
<https://doi.org/10.1533/9781908818249.481>.

</div>

<div id="ref-the_r_foundation_for_statistical_computing_r:_2018">

The R Foundation for Statistical Computing. 2018. “R: Regulatory
Compliance and Validation IssuesA Guidance Document for the Use of R in
Regulated ClinicalTrial Environments.” The R Foundation for Statistical
Computing. <https://www.r-project.org/doc/R-FDA.pdf>.

</div>

<div id="ref-vogel_medical_2011">

Vogel, David A. 2011. *Medical Device Software Verification, Validation
and Compliance*. Boston: Artech House.
<http://site.ebrary.com/id/10436227>.

</div>

</div>
