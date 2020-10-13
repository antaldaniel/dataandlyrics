+++
# Project title.
title = "Data Observatory"

# Date this page was created.
date = 2019-02-27T00:00:00

# Project summary to display on homepage.
summary = "Automated Data Observatory based on the principles of reproducible research"

# Tags: can be used for filtering projects.
tags = ["ceemid", "surveys", "music-industry", "observatory", "reprodubile-research"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Links (optional).
url_pdf = ""
url_slides = ""
url_video = ""
url_code = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
#url_custom = [{icon_pack = "fab", icon="twitter", name="Follow", url = "https://twitter.com/georgecushen"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = ""
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
+++

An **observatory** is a location used for observing terrestrial or celestial events. The European Commission and the Council of Europe are supporting numerous data observatories to support research and development and evidence-based policymaking. We are creating automated observatories following the best practices of reproducible research.

Satellite Report grew out of a such an observatory, [CEEMID](https://ceemid.eu/). 

## How To Start A Data Observatory?

* A **private observatory** is a data integration system, which automatically collects external information, processes it and professionally joins it with internal data resources. We offer this to [business](#business), [scientific research](#science), [think tank and NGO](#ngo) and [journalism](#journalism) partners.

* A **collaborative observatory** is a data integration system that has a map to collaborating institutions’s data resources, and is able to exploit their synergies by automatically combining their data, triggered by an authorization of all involved parties. We offer this to Consortia of various entities. Daniel's [CEEMID project](https://danielantal.eu/project/ceemid/) developed since 2014 is a good example of a collaborative observatory.

* A **public observatory** is a collaborative observatory that intends to make at least some of its data assets available as open data. ode chunk to prevent printing of the R code that generated the plot. We offer this for the European Union and its Consortia. [See some observatories »](https://documentation.satellitereport.com/index.php?title=Observatory)

Our observatories fulfil important functions in data collection, processing, integration, and automated modelling. We provide these services as custom software as service products in the form of data applications. To design a good observatory that fulfils your business, policy, scientific or journalistic needs, we provide data curating as a consulting service.

A few public observatories:

* The [European Alternative Fuels Observatory](https://www.eafo.eu/) is an European Commission funded initiative which provides open and free information, amongst others to support Member States with the implementation of EU Directive 2014/94 on the deployment of alternative fuels infrastructure. The EAFO is maintained by the [EAFO Consortium](https://www.eafo.eu/knowledge-center/consortium).

* The [EU Energy Poverty Observatory](https://www.energypoverty.eu/about/about-observatory) (EPOV) is an initiative by the European Commission to help Member States in their efforts to combat energy poverty. It exists to improve the measuring, monitoring and sharing of knowledge and best practice on energy poverty, and it is developed by a consortium of universities, think tanks, and the business sector.

* The [European Observatory for Clusters and Industrial Change](https://www.clustercollaboration.eu/eu-initiatives/european-cluster-observatory) to help Europe's regions and countries in designing better and more evidence-based cluster policies and initiatives. This platform is funded by the EU programme for
the Competitiveness of Enterprises and SMEs (COSME).

* The [Cluster Observatory](http://www.clusterobservatory.eu/) of the Center for Strategy and Competitiveness at the Stockholm School of Economics, which started out originally as the European Cluster Observatory.

## Reproducible research

We believe that a modern data observatory should be as much reproducible and automated as possible.

* Following reproducible research principles leads to higher data quality, especially if it is based on open-source code.  
* Reproducible data can be automatically documented, which makes teamwork, collaboration and instant use far more efficient.
* Reproducible research products offer far more efficient supervision and audit.  Quality control is cheaper and easier.

## Open source, open data, open collaboration

In the EU, open data is governed by the [Directive on open data and the re-use of public sector information - in short: Open Data Directive (EU) 2019 / 1024](https://eur-lex.europa.eu/legal-content/EN/TXT/?qid=1561563110433&uri=CELEX:32019L1024). It entered into force on 16 July 2019. It replaces the [Public Sector Information Directive](https://eur-lex.europa.eu/legal-content/en/ALL/?uri=CELEX:32003L0098), also known as the ‘PSI Directive’ which dated from 2003 and was subsequently amended in 2013. The public sector offers tens of billions' euro worth data --- but without a free lunch.  While the data is available free or at marginal cost, it is processed to the needs of public authorities, public services, and require special know-how to be put to a secondary business or research use. Our founder, [Daniel](https://satellitereport.com/author/daniel/), has been involved in Open Data and PSI since 2003. Our expertise guarrantee that in the field of economics, finance, social sciences, and most policy areas your observatory starts with hundreds, or even thousands of re-used public sector indicators, often with a decade-long or even longer history.

We use the open source [statistical programming language R](https://documentation.ceemid.eu/index.php?title=R_(programming_language)), and various open source R programs.  We also release some of our mission-critical code developed to create business and policy indicators --- see [eurobarometer](https://satellitereport.com/publication/eurobarometer_2020/), [iotables](https://satellitereport.com/publication/iotables_2018/), [regions](https://satellitereport.com/publication/regions_2020/), [retroharmonize](http://retroharmonize.satellitereport.com/). Our important code goes through anonymous peer-review, and open for external review, audit. For example, this allowed us to compare test results on calculating economic impact indicators for the creative industries and other industries with the [UK statistical office](http://iotables.ceemid.eu/articles/united_kingdom_2010.html). You can even modify our code -- you just cannot copyright and close it for commercial use. In our view, this guarrantees the highest quality, but it also gives assurrances of transparency and makes vendor lock-in impossible. While developing these packages requires our special knowledge, their rich and peer-reviwedd documentation makes sure that you can always find a team member, or hire a data analyst who can work with them without us.

The use of open source software and the open source R statistical language allows a continuous peer-review of data ingestion, processing, corrections and indicator creation by statisticians, data scientists and academics.  Statistical products of national statistical offices, sometimes Eurostat itself, not to mention data providers that are not part of the system of national statistical offices, such as the European Audiovisual Observatory, are plagued with data errors that are corrected and amended relatively slowly.

## Data integration instead of centralisation

Our observatories by design are flexible and decentralized. Our continuous [data integration](https://documentation.ceemid.eu/index.php?title=Main_Page#Data_Integration) allows to join and publish any data the observatory and its member have access to, and have rights and intentions to share or publish. We only keep metadata, i.e. a 'data map' to make sure that whatever the Observatory's members want to share or publish is always automatically available for processing and publication.
