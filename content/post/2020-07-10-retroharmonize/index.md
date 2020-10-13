+++
title = "Increase The Value Of Market Research With Open Data And Survey Harmonization"

date = 2020-07-09T15:00:00
lastmod = 2020-09-21T11:00:00
draft = false

authors = ["Daniel Antal, CFA"]

tags = ["R", "open-data", "surveys", "harmonization"]

summary = "The very techincal terms of *ex ante* , *ex post* or retrospective harmonization hide opportunities that can significantly increase the value for money in empirical market research, potentially increasing the value of a high-cost, high-value survey to multiple times of its euro value."

# Featured image
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Left"

  # Show image only in page previews?
  preview_only = false

+++


In the last weeks I have been releasing the early source code of two R packages, [retroharmonize](https://dataobservatory.eu/publication/retorharmonize_2020/) for the *ex post* harmonization infrastructure of surveys, and  [eurobarometer](https://dataobservatory.eu/publication/eurobarometer_2020/) for Eurobarometer-specific work, complemented by my earlier release of [regions](https://dataobservatory.eu/publication/regions_2020/), which tracks about 20,000 regional boundary changes of French departments, Polish voivodeships and Hungarian counties, and other sub-national divisions of about 32 European countries.

The very technical terms of *ex ante* , *ex post* or retrospective harmonization hide opportunities that can significantly increase the value for money in empirical market research, potentially increasing the value of a high-cost, high-value survey to multiple times of its euro value.

In my work, I have used *ex ante* harmonized questionnaires with EU survey programs, for example, the harmonized CAP surveys to determine the characteristics of concert audiences in a country, or people who download music to their computers.  The EU has been opening up its own survey programs in a piecemeal fashion, and surveys used by the European Commission, the Parliament, or even the national statistical offices are becoming more and more available.  After harmonizing the questions, I can apply *ex post* harmonization of the results, too, resulting in a far more valuable research document:

1.	I can usually compare the basic values, such as concert visiting likelihood in the past – for example, I surveyed Hungary and Slovakia first in 2015, but immediately could compare with 2013 and 2007 data.

![Harmonized concert visiting questions over time](/img/dataanimation/concert_hu_animation_smooth.gif)

2.	I get international benchmarks for free, for example, German, Czech, French data.

![Harmonized concert visiting questions accross countries](/img/music/cee_concert_demography_16x9.jpg)

3.	Using the hierarchical nature of CAP surveys, I can make reasonable estimates of details that I survey only in one or few countries, such as visiting jazz concerts, and not concert only; or copying non-licensed music to devices.

Of course, there is no free lunch here.  I can access millions of euros values of survey data, but nobody will make prepare it for my use. These surveys were processed for different users and different uses and joining them with my data is a very difficult task that I had been doing better and better in the past 5 years. To make this work as error-free as possible, I will publish the critical elements of the code as open source software on CRAN soon - the github release is an early version of this.

Much of the current momentum is due to a new contributor to these packages, [Marta Kołczyńska](https://martakolczynska.com/), who is an excellent R programmer and a bright academic in international survey harmonization and reproducible research.

## Related 

* The website of the  [retroharmonize](https://retroharmonize.dataobservatory.eu/) package
* The website of the [eurobarometer](https://eurobarometer.dataobservatory.eu/) package
* The website of the [regions](http://regions.dataobservatory.eu/) package
