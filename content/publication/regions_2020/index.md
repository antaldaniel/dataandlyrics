+++
title = "regions R package"
date = 2020-06-03T17:00:00
draft = false

authors = ["Daniel Antal"]

# Publication type.
# Legend:

publication_types = ["0"]

# Abstract and optional shortened version.
abstract = "An open source R package for validating sub-national statistical typologies, re-coding across standard typologies of sub-national statistics, and making valid aggregate level imputation, re-aggregation, re-weighting and projection down to lower hierarchical levels to create meaningful data panels and time series."

abstract_short = "regions currently takes care of 20,000 sub-divisional boundary changes in Europe since 1999."

# Is this a featured publication? (true/false)
featured = true

# Projects (optional).
projects = ["R", "opendata"]

categories = ["R"]

tags = ["r-bloggers", "regions", "geography"]

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Links (optional).
url_pdf = ""
url_preprint = ""
url_code = ""
url_dataset = ""
url_project = "https://regions.dataobservatory.eu/"
url_slides = ""
url_video = ""
url_poster = ""
url_source = "https://github.com/rOpenGov/regions/"

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
url_custom = [{name = "Github repo", url = "https://github.com/antaldaniel/regions/"}, {name = "regions on CRAN", url = "https://cran.r-project.org/web/packages/regions/index.html"}]

# Digital Object Identifier (DOI)
doi = "10.5281/zenodo.3825696"

# Does this page contain LaTeX math? (true/false)
math = false

# Featured image
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "TopLeft"
+++


## Installation

You can install the development version from
[GitHub](https://github.com/) with:

``` r
devtools::install_github("rOpenGov/regions")
```

or the released version from CRAN:

``` r
install.packages("devtools")
```

[regions](https://regions.dataobservatory.eu/) currently takes care of 20,000 sub-divisional boundary changes in Europe since 1999. Comparing departments of France in 2013, with 2007 vojvodinas of Poland and 2018 megyék in Hungary? This extremely errorprone work is automated, as a result, you can compare 110-260 regions for far better analysis. regions was downloaded about 600 researchers in the first month after release.

You can review the complete package documentation on
[regions.dataobservatory.eu](https://regions.dataobservatory.eu/). If you find
any problems with the code, please raise an issue on
[Github](https://github.com/antaldaniel/regions). Pull requests are
welcome if you agree with the [Contributor Code of
Conduct](https://contributor-covenant.org/version/2/0/CODE_OF_CONDUCT.html)

If you use `regions` in your work, please [cite the
package](https://doi.org/10.5281/zenodo.3825696).

## Motivation

Working with sub-national statistics has many benefits. In policymaking or in social sciences, it is a common practice to compare national statistics, which can be hugely misleading. The United States of America, the Federal Republic of Germany, Slovakia and Luxembourg are all countries, but they differ vastly in size and social homogeneity. Comparing Slovakia and Luxembourg to the federal states or even regions within Germany, or the states of Germany and the United States can provide more adequate insights. Statistically, the similarity of the aggregation level and high number of observations can allow more precise control of model parameters and errors.

The advantages of switching from a national level of the analysis to a
sub-national level comes with a huge price in data processing,
validation and imputation. The package Regions aims to help this
process.

This package is an offspring of the
[eurostat](http://ropengov.github.io/eurostat/) package on
[rOpenGov](http://ropengov.github.io/). It started as a tool to validate and re-code regional Eurostat statistics, but it aims to be a general solution for all sub-national statistics. It will be developed parallel with other rOpenGov packages.

## Sub-national Statistics Have Many Challenges

  - **Frequent boundary changes**: as opposed to national boundaries,
    the territorial units, typologies are often change, and this makes
    the validation and recoding of observation necessary across time.
    For example, in the European Union, sub-national typologies change
    about every three years and you have to make sure that you compare
    the right French region in time, or, if you can make the time-wise
    comparison at all.

  - **Hierarchical aggregation and special imputation**: missingness is
    very frequent in sub-national statistics, because they are created
    with a serious time-lag compared to national ones, and because they
    are often not back-casted after boundary changes. You cannot use
    standard imputation algorithms because the observations are not
    similarly aggregated or averaged. Often, the information is
    seemingly missing, and it is present with an obsolete typology code.

## Package functionality

  - Generic vocabulary translation and joining functions for
    geographically coded data
  - Keeping track of the boundary changes within the European Union
    between 1999-2021
  - Vocabulary translation and joining functions for standardized
    European Union statistics
  - Vocabulary translation for the `ISO-3166-2` based Google data and
    the European Union
  - Imputation functions from higher aggregation hierarchy levels to
    lower ones, for example from `NUTS1` to `NUTS2` or from `ISO-3166-1`
    to `ISO-3166-2` (impute down)
  - Imputation functions from lower hierarchy levels to higher ones
    (impute up)
  - Aggregation function from lower hierarchy levels to higher ones, for
    example from NUTS3 to `NUTS1` or from `ISO-3166-2` to `ISO-3166-1`
    (aggregate; under development)
  - Disaggregation functions from higher hierarchy levels to lower ones,
    again, for example from `NUTS1` to `NUTS2` or from `ISO-3166-1` to
    `ISO-3166-2` (disaggregate; under development)

## Vignettes / Articles

  - [Working With Regional, Sub-National Statistical
    Products](http://regions.danielantal.eu/articles/Regional_stats.html)
  - [Validating Your
    Typology](http://regions.danielantal.eu/articles/validation.html)
  - [Recoding And
    Relabelling](http://regions.danielantal.eu/articles/recode.html)
  - [The Typology Of The Google Mobility Reports
    (COVID-19)](http://regions.danielantal.eu/articles/google_mobility_report.html)

## Feedback?

Raise and [issue](https://github.com/antaldaniel/eurobarometer/issues) on Github or [get in touch](https://danielantal.eu/#contact). Downloaders from CRAN: 
[![metacran
downloads](https://cranlogs.r-pkg.org/badges/regions)](https://cran.r-project.org/package=regions)
