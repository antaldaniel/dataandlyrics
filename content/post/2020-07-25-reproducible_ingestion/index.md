+++
title = "Reproducible data ingestion in practice"

date = 2020-07-24T15:00:00
lastmod = 2020-07-24T15:00:00
draft = false

authors = ["Daniel Antal, CFA"]

tags = ["R", "open-data", "reproducible"]

summary = "If your analytical work has used a certain type of data at least two times in the past, it is likely that the data will be needed again.  This is a good time to make the data ingestion automatic and reproducible."

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


## How does a reproducible data ingestion look like in practice? 

If your analytical work has used a certain type of data at least two times in the past, it is likely that the data will be needed again.  This is a good time to make the data ingestion automatic and reproducible.  We demonstrate a simple data ingestion from Eurostat.  Daniel is part of the [rOpenGov](http://ropengov.github.io/) collective that maintains the [eurostat](https://github.com/ropengov/eurostat) package for reproducible access to the European statistical agencies data warehouse.


```r
library(eurostat)
nuts3_population_raw <- get_eurostat ("demo_r_pjangrp3") 
nuts3_population_metadata <- get_eurostat_toc() %>%
  filter ( code == "demo_r_pjangrp3" ) %>%
  distinct_all () 

last_update <- nuts3_population_metadata$`last update of data`
first_data <- nuts3_population_metadata$`data start`
```

The metadata entries to this statistics suggest that the latest data is from Thursday 14 May, 2020, so it is high time to refresh your data tables and update your charts. Sadly, the metadata suggest that on this occasion the table went through structural changes, so you may get a different spreadsheet table when you downloaded compared to the last occasion.  You may think that this is another reason to automate the ingestion into a well-defined, tidy table format.

<table class="table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:left;"> title </th>
   <th style="text-align:left;"> code </th>
   <th style="text-align:left;"> last update of data </th>
   <th style="text-align:left;"> last table structure change </th>
   <th style="text-align:left;"> data start </th>
   <th style="text-align:left;"> data end </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> Population on 1 January by age group, sex and NUTS 3 region </td>
   <td style="text-align:left;"> demo_r_pjangrp3 </td>
   <td style="text-align:left;"> 14.05.2020 </td>
   <td style="text-align:left;"> 14.05.2020 </td>
   <td style="text-align:left;"> 2014 </td>
   <td style="text-align:left;"> 2019 </td>
  </tr>
</tbody>
</table>

Looking at the head of this raw data, you realize that this is not table, but a little database! It contains population divisions by sex and age groups.  However, your indicator is the total population of each `NUTS3` regions, so let’s filter out only the total population for both sexes.

<table class="table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:left;"> sex </th>
   <th style="text-align:left;"> unit </th>
   <th style="text-align:left;"> age </th>
   <th style="text-align:left;"> geo </th>
   <th style="text-align:left;"> time </th>
   <th style="text-align:right;"> values </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> T </td>
   <td style="text-align:left;"> NR </td>
   <td style="text-align:left;"> Y_LT5 </td>
   <td style="text-align:left;"> NO07 </td>
   <td style="text-align:left;"> 2018-01-01 </td>
   <td style="text-align:right;"> 25108 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> M </td>
   <td style="text-align:left;"> NR </td>
   <td style="text-align:left;"> Y10-14 </td>
   <td style="text-align:left;"> DED44 </td>
   <td style="text-align:left;"> 2014-01-01 </td>
   <td style="text-align:right;"> 4620 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> F </td>
   <td style="text-align:left;"> NR </td>
   <td style="text-align:left;"> Y45-49 </td>
   <td style="text-align:left;"> FRB </td>
   <td style="text-align:left;"> 2014-01-01 </td>
   <td style="text-align:right;"> 88590 </td>
  </tr>
</tbody>
</table>

Looking at the head of this raw data, you realize that this is not table, but a little database! It contains population divisions by sex and age groups.  However, your indicator is the total population of each `NUTS3` regions, so let’s filter out only the total population for both sexes.


```r
nuts3_population <- nuts3_population_raw %>%
  filter ( sex == "T",             # for both sexes
           age == "TOTAL") %>%     # for all age groups
  mutate ( year = as.integer(substr(as.character(time), 1,4)), 
           indicator = paste0("population_sex-", sex, "_unit-", unit, 
                               "_age-", age)) %>%
  select ( -all_of(c("sex", "unit", "age"))) 
```

The following table is already tidy --- each observation corresponds with a small region of Europe.  The filtering information as metadata is included in the indicator's name.

<table class="table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:left;"> geo </th>
   <th style="text-align:left;"> time </th>
   <th style="text-align:right;"> values </th>
   <th style="text-align:right;"> year </th>
   <th style="text-align:left;"> indicator </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> HU222 </td>
   <td style="text-align:left;"> 2015-01-01 </td>
   <td style="text-align:right;"> 253997 </td>
   <td style="text-align:right;"> 2015 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
  <tr>
   <td style="text-align:left;"> NO </td>
   <td style="text-align:left;"> 2014-01-01 </td>
   <td style="text-align:right;"> 5107970 </td>
   <td style="text-align:right;"> 2014 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
  <tr>
   <td style="text-align:left;"> ES704 </td>
   <td style="text-align:left;"> 2016-01-01 </td>
   <td style="text-align:right;"> 112087 </td>
   <td style="text-align:right;"> 2016 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
  <tr>
   <td style="text-align:left;"> FRK12 </td>
   <td style="text-align:left;"> 2015-01-01 </td>
   <td style="text-align:right;"> 146219 </td>
   <td style="text-align:right;"> 2015 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
  <tr>
   <td style="text-align:left;"> DE3 </td>
   <td style="text-align:left;"> 2018-01-01 </td>
   <td style="text-align:right;"> 3613495 </td>
   <td style="text-align:right;"> 2018 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
  <tr>
   <td style="text-align:left;"> NL225 </td>
   <td style="text-align:left;"> 2019-01-01 </td>
   <td style="text-align:right;"> 400685 </td>
   <td style="text-align:right;"> 2019 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
</tbody>
</table>

![](data_ingest_files/figure-html/choropleth-1.png)<!-- -->

The population size is rather homogeneous --- no wonder, the small regions of Europe are exactly defined to be roughly of equal size and easily comparable. 

You are wondering how you could match this data with your own records, or data acquired from Google about number of restaurants or searchers for concerts?

<table class="table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:left;"> geo </th>
   <th style="text-align:left;"> time </th>
   <th style="text-align:right;"> values </th>
   <th style="text-align:right;"> year </th>
   <th style="text-align:left;"> indicator </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> IE042 </td>
   <td style="text-align:left;"> 2017-01-01 </td>
   <td style="text-align:right;"> 451293 </td>
   <td style="text-align:right;"> 2017 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
  <tr>
   <td style="text-align:left;"> SI044 </td>
   <td style="text-align:left;"> 2014-01-01 </td>
   <td style="text-align:right;"> 112848 </td>
   <td style="text-align:right;"> 2014 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
  <tr>
   <td style="text-align:left;"> DE225 </td>
   <td style="text-align:left;"> 2015-01-01 </td>
   <td style="text-align:right;"> 77927 </td>
   <td style="text-align:right;"> 2015 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
  <tr>
   <td style="text-align:left;"> PL621 </td>
   <td style="text-align:left;"> 2016-01-01 </td>
   <td style="text-align:right;"> 523096 </td>
   <td style="text-align:right;"> 2016 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
  <tr>
   <td style="text-align:left;"> TRB13 </td>
   <td style="text-align:left;"> 2018-01-01 </td>
   <td style="text-align:right;"> 273354 </td>
   <td style="text-align:right;"> 2018 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
  <tr>
   <td style="text-align:left;"> FRK24 </td>
   <td style="text-align:left;"> 2018-01-01 </td>
   <td style="text-align:right;"> 1261373 </td>
   <td style="text-align:right;"> 2018 </td>
   <td style="text-align:left;"> population_sex-T_unit-NR_age-TOTAL </td>
  </tr>
</tbody>
</table>

There is no easy solution for this problem.  Within the EU in the last 20 years there were several thousand internal boundary changes --- states, provinces, regions are rather free to change their internal administration boundaries. Regions are constantly changing their names or their spelling, too. Sometimes they use a standard English translation of their region, sometimes only the national language variants.  In Greece or Bulgaria they do not even use the Latin alphabet!

[Daniel](https://satellitereport.com/author/daniel/) and [Istvan](https://satellitereport.com/author/istvan-zsoldos/) created and released an open-source code library, [regions](http://regions.danielantal.eu/) to deal with similar issues. It allows the changes between boundary definition between 1999-2021, or the connection of the globally used geographical typology adopted by Google with Eurostat's EU-only definitions.

For example, you can already foresee that there are future changes (to be implemented from the year 2021) that will affect two of these regions.


```r
set.seed(21)
validate_for_2021 <- nuts3_population  %>%
  select ( -all_of(c("time", "indicator")) ) %>%
  sample_n(8) %>%
  regions::validate_nuts_regions(., nuts_year = 2021 ) 
```
<table class="table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:left;"> geo </th>
   <th style="text-align:right;"> values </th>
   <th style="text-align:right;"> year </th>
   <th style="text-align:left;"> typology </th>
   <th style="text-align:left;"> valid_2021 </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> DE248 </td>
   <td style="text-align:right;"> 115681 </td>
   <td style="text-align:right;"> 2018 </td>
   <td style="text-align:left;"> nuts_level_3 </td>
   <td style="text-align:left;"> TRUE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> BG422 </td>
   <td style="text-align:right;"> 228141 </td>
   <td style="text-align:right;"> 2019 </td>
   <td style="text-align:left;"> nuts_level_3 </td>
   <td style="text-align:left;"> TRUE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> UKN13 </td>
   <td style="text-align:right;"> 139774 </td>
   <td style="text-align:right;"> 2014 </td>
   <td style="text-align:left;"> NA </td>
   <td style="text-align:left;"> FALSE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> FRH0 </td>
   <td style="text-align:right;"> 3276543 </td>
   <td style="text-align:right;"> 2014 </td>
   <td style="text-align:left;"> nuts_level_2 </td>
   <td style="text-align:left;"> TRUE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> DEB3 </td>
   <td style="text-align:right;"> 2031780 </td>
   <td style="text-align:right;"> 2016 </td>
   <td style="text-align:left;"> nuts_level_2 </td>
   <td style="text-align:left;"> TRUE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> ITG25 </td>
   <td style="text-align:right;"> 335097 </td>
   <td style="text-align:right;"> 2014 </td>
   <td style="text-align:left;"> NA </td>
   <td style="text-align:left;"> FALSE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> DE71A </td>
   <td style="text-align:right;"> 232848 </td>
   <td style="text-align:right;"> 2016 </td>
   <td style="text-align:left;"> nuts_level_3 </td>
   <td style="text-align:left;"> TRUE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> FI1D5 </td>
   <td style="text-align:right;"> 68677 </td>
   <td style="text-align:right;"> 2014 </td>
   <td style="text-align:left;"> nuts_level_3 </td>
   <td style="text-align:left;"> TRUE </td>
  </tr>
</tbody>
</table>

There is trouble ahead, but we have a table that is tidy and works for the time being.  Let's save it and document it. 


```r
eurostat::get_bibentry("demo_r_pjangrp3")
```

```
## @Misc{demo_r_pjangrp3_14-05-2020,
##   title = {Population on 1 January by age group, sex and NUTS 3 region [demo_r_pjangrp3]},
##   url = {https://ec.europa.eu/eurostat/web/products-datasets/-/demo_r_pjangrp3},
##   language = {en},
##   year = {14.05.2020},
##   publisher = {Eurostat},
##   author = {{Eurostat}},
##   urldate = {2020-07-25},
## }
```

## What is reproducibility in this case?

**Replicability** means that somebody else in your team can get exactly the same data as in this post. 

* Recording exactly what have your analysts downloaded, including source, date, filtering settings

**Reproducibility** means that not only your team, but an external auditor or a peer reviewer can easily validate that your data is sound. All our solutions are opens source, and use the most popular statistical programming language, R. Anybody with a basic knowledge of R, or probably even SQL (we use an extension of R that uses SQL-like syntax) can read if everything goes allright. Your team can even modify the code.

* Creating a documentation that you updates your reports data citations

**Confirmability** means that somebody who is not using . All our solutions are opens source, and use the most popular statistical programming language, R.  R is supported by Microsofts BI products, SPSS and other statistical software, too. We are not a software company, there is no vendor lock-in, and our work can be confirmed with other statistical software.

* Data acquired via our data gathering apps is automatically documented, follows tidy formats and valid abbreviations, and can be confirmed in a wide range of statistical and spreadsheet applications, including SPSS, Excel, OpenOffice, Google Spreadsheets.
* Bringing the data to a tidy format which is easy to join with other data in a spreadsheet application, or stored in a relational database.
* Validating the data structure, in this case, with special attention to regional boundaries and regional names.

**Auditability** means that external auditors can validate that the data your team uses from our app is correct. 

* We are following methodological guidelines and definitions set by international bodies such as Eurostat's ESSNet statistical network or IFRS. 
* Our critical software code is not only open source, but goes through various levels of statistical peer-review. We are sending for scientific validation and peer-review our methodology, too.
* Being open source allows us to make any corrections, updates, should any problem or standard change affect the data.


<div id="references" class="section level2 unnumbered">
<h2>References</h2>
<div id="refs" class="references">
<div id="ref-R-regions">
<p>Antal, Daniel. 2020. <em>Regions: Processing Regional Statistics</em>. <a href="https://regions.danielantal.eu/">https://regions.danielantal.eu/</a>.</p>
</div>
<div id="ref-demo_r_pjangrp3_14-05-2020">
<p>Eurostat. n.d. Eurostat. Accessed July 25, 2020. <a href="https://ec.europa.eu/eurostat/web/products-datasets/-/demo_r_pjangrp3">https://ec.europa.eu/eurostat/web/products-datasets/-/demo_r_pjangrp3</a>.</p>
</div>
<div id="ref-R-eurostat">
<p>Lahti, Leo, Janne Huovari, Markus Kainu, and Przemyslaw Biecek. 2020. <em>Eurostat: Tools for Eurostat Open Data</em>. <a href="https://CRAN.R-project.org/package=eurostat">https://CRAN.R-project.org/package=eurostat</a>.</p>
<div id="ref-R-eurostat">
<p>Hadley Wickham. 2014. <em>Tidy Data</em>.Journal of Statistical Software vol 59, no 10.<a href="https://www.jstatsoft.org/v059/i10">https://www.jstatsoft.org/v059/i10</a>.</p>
</div>
</div>
</div>
