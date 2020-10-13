+++
title = "retroharmonize R package for survey harmonization"
date = 2020-08-25T16:00:00
draft = false

authors = ["Daniel Antal", "Marta Kolczynska"]

# Publication type.
# Legend:

publication_types = ["0"]

# Abstract and optional shortened version.
abstract = "The goal of retroharmonize is to facilitate retrospective (ex-post) harmonization of data, particularly survey data, in a reproducible manner. The package provides tools for organizing the metadata, standardizing the coding of variables, variable names and value labels, including missing values, and for documenting all transformations, with the help of comprehensive S3 classes."

abstract_short = "The goal of retroharmonize is to facilitate retrospective (ex-post) harmonization of data, particularly survey data, in a reproducible manner."

# Is this a featured publication? (true/false)
featured = true

# Projects (optional).
projects = ["R", "opendata"]
categories = ["R"]
tags = ["r-bloggers", "eurobarometer", "surveys"]

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
url_project = "https://eurobarometer.dataobservatory.eu/"
url_slides = ""
url_video = ""
url_poster = ""
url_source = "https://github.com/antaldaniel/eurobarometer"

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
url_custom = [{name = "Github Repo", url = "https://github.com/antaldaniel/eurobarometer/"}]

# Digital Object Identifier (DOI)
doi = "10.5281/zenodo.3901724"

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

The aim of `retroharmonize` is to provide tools for reproducible
retrospective (ex-post) harmonization of datasets that contain variables
measuring the same concepts but coded in different ways. Ex-post data
harmonization enables better use of existing data and creates new
research opportunities. For example, harmonizing data from different
countries enables cross-national comparisons, while merging data from
different time points makes it possible to track changes over time.

Retrospective data harmonization is associated with challenges including
conceptual issues with establishing equivalence and comparability,
practical complications of having to standardize the naming and coding
of variables, technical difficulties with merging data stored in
different formats, and the need to document a large number of data
transformations. The `retroharmonize` package assists with the latter
three components, freeing up the capacity of researchers to focus on the
first.

Specifically, the `retroharmonize` package proposes a reproducible
workflow, including a new class for storing data together with the
harmonized and original metadata, as well as functions for importing
data from different formats, harmonizing data and metadata, documenting
the harmonization process, and converting between data types. See
[here](https://retroharmonize.dataobservatory.eu/reference/retrohamonize.html)
for an overview of the functionalities.

The new `labelled_spss_survey()` class is an extension of [haven’s
labelled\_spss
class](https://haven.tidyverse.org/reference/labelled_spss.html). It not
only preserves variable and value labels and the user-defined missing
range, but also gives an identifier, for example, the filename or the
wave number, to the vector. Additionally, it enables the preservation –
as metadata attributes – of the original variable names, labels, and
value codes and labels, from the source data, in addition to the
harmonized variable names, labels, and value codes and labels. This way,
the harmonized data also contain the pre-harmonization record. The
stored original metadata can be used for validation and documentation
purposes.

The vignette [Working With The labelled\_spss\_survey
Class](https://retroharmonize.dataobservatory.eu/articles/labelled_spss_survey.html)
provides more information about the `labelled_spss_survey()` class.

In [Harmonize Value
Labels](https://retroharmonize.dataobservatory.eu/articles/harmonize_labels.html)
we discuss the characteristics of the `labelled_spss_survey()` class and
demonstrates the problems that using this class solves.

We also provide two extensive case studies illustrating how the
`retroharmonize` package can be used for ex-post harmonization of data
from cross-national surveys on the example of the
[Afrobarometer](https://retroharmonize.dataobservatory.eu/articles/afrobarometer.html)
and the
[Eurobarometer](https://retroharmonize.dataobservatory.eu/articles/eurobarometer.html).
The creators of `retroharmonize` are not affiliated with either
Afrobarometer, Eurobarometer, or the organizations that designs,
produces or archives their surveys.

## Code of Conduct

Please note that the `retroharmonize` project is released with a
[Contributor Code of
Conduct](https://www.contributor-covenant.org/version/2/0/code_of_conduct/).
By contributing to this project, you agree to abide by its terms.
