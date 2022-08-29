---
# Project title.
title: "Digital Music Observatory"

# Date this page was created.
date: 2020-08-26T08:00:00

# Project summary to display on homepage.
summary: "Collaborative reproducible research in the music industry"

# Tags: can be used for filtering projects.
tags: 
  - Digital Music Observatory

# Optional external URL for project (replaces project detail page).
external_link: ""

# Slides (optional).
#   Otherwise, set `slides: ""`.
slides: ""

# Links (optional).
url_pdf: ""
url_slides: ""
url_video: ""
url_code: ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
#url_custom: [{icon_pack: "fab", icon="twitter", name="Follow", url: "https://twitter.com/georgecushen"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
image:
  # Caption (optional)
  caption: "The royalty gap within Europe"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point: "Smart"
---

We are developing our [Demo Music Observatory](https://music.dataobservatory.eu/) in the world's 2nd ranked university-backed incubator program, the [Yes!Delft AI Validation Lab](post/2020-09-25-yesdelft-validation/). Our aim is to show a better organizational model, examples of research automation and other data integration innovation that can reduce the budgetary needs of the European Music Observatory by 80-90% and provide far more timely, accurate, and relevant service than most data observatories in Europe.

1. [Background](#background)
2. [Data gaps](#data-gaps)
3. [Organization and institutional model](#organization)
4. [Quality Control](#quality)
5. [Value For Money, Budget](#budget)
6. [Use Cases](#use-cases)

## Background {#background}

Data is power, and `big data creates injustice`.  Organizations that control large amounts of data, for example, the entire listening history of hundreds of millions of people in all major countries of the world, can train algorithms and robots that drive most of the music in the world.  They can make your investment into a sound recording successful or doomed. They can circumvent or help a local content regulation, reinforce, or disable a national cultural policy goal.  A country may introduce national artist quotas on radio, if all the youth will be personally recommended foreign songs in their music discovery age in the very same country.

We believe that answer of the EU and UNESCO with the creation of permanent data collection points, so-called [data observatories](https://dataobservatory.eu/faq/observatories/) is correct. However, after reviewing 62 data observatories, we are convinced that many data observatories are doomed to fail. 

Our private observatory, CEEMID was consulted in the creation of the [Feasibility study for the establishment of a European Music Observatory](https://op.europa.eu/en/publication-detail/-/publication/a756542a-249d-11eb-9d7e-01aa75ed71a1/language-en/format-PDF/source-171307257), and some of our recommendations found way into the consultant’s document. We created a Demo Music Observatory to provide a practical guidance on the decisions facing the European stakeholders, and to answer the questions that were left open in the Feasibility Study --- particularly on  [data integration](#data-gaps) and the [institutional model](#organization), where a wrong choice can lead to very long delivery time, [quality control](#quality) and [budgeting](#budget).

## Data Gaps {#data-gaps}
According to the feasibility study, 11% of the stakeholders consulted found that sufficient data was available for their work, 30% said that there could be more data but that does not affect their work, and 59% found that the lack of data affects their work.

We have shown in the [Central & Eastern European Music Industry Report 2020](/publication/ceereport_2020/), featured in the [CCS Ecosystems: FLIPPING THE ODDS Conference](/post/2020-01-30-ceereport/) – a two-day high-level stakeholder event jointly organized by Geothe-Institute and the DG Education and Culture of the European Commission with the Creative FLIP project.that much of the data gap is [illusory](/post/2020-01-30-ceereport/#invisibility): the fragmented nature of the music industry, the lack of in-house data expertise create bottlenecks in the use of the data. However, the data is present, and as it is stated in 148-149, we are willing to transfer thousands of indicators in all pillars to the future European Music Observatory.

Our Demo Music Observatory is based on the accepted music industry concept in the US and the EU (the three-income stream model) and its data maps that we could apply to emerging markets -- for example, in [the case of Croatia](/post/2016-04-20_makk15/). A clear map of the industry and a clear map of the data reveals that much of the perceived gap is illusory.  We would like to challenge the European music stakeholders to test us, request seemingly missing data that we will try to publish.

{{< figure library="true" src="/methodology/three_income_streams_croatia.png" title="Illustration: our map to find to locate data in the Croatian music industry. Our Demo Music Observatory is based on the accepted music industry concept in the US and the EU (the three-income stream model) and its data maps." >}}

This remains a problem with the Summary of Data Gaps on pages 128-131 that enumerate the perceived lack of data for the three pillars.  We believe that these data gaps are in most cases illusory, and the remedies offered in the study are often misplaced.

## Circulation of Repertoire & Cultural Diversity 

> Streaming activity: the Feasibility Study offers Nielsen’s Global Charts as a potential solution, even though we have shown that this is not the right approach.

The problem with Nielsen’s charts, or any chart provider’s chart, is that it covers less than 0.01% of the European repertoire, and it depicts a completely irrelevant picture for the 99.99% of the European stakeholders.

{{< figure library="true" src="/reports/medianvalue-1.png" title="Illustration: our map to find to locate data in the Croatian music industry. Our Demo Music Observatory is based on the accepted music industry concept in the US and the EU (the three-income stream model) and its data maps." >}}

We believe that the right approach, followed by our Demo Music Observatory, is a reconciliation with the work on [Big Data](https://ec.europa.eu/eurostat/cros/content/big-data_en) the  European Statistical System (i.e. the partnership of Eurostat and the national statistical authorities.) (See [our analysis](https://ceereport2020.ceemid.eu/market.html#recmarket) of 20 advanced, emerging and future markets in Europe.)

`Challenge Our Demo Observatory`: *Check out the* [Music Diversity & Circulation Pillar](https://demoobservatory.dataobservatory.eu/music-diversity-circulation.html) *of our Demo Music Observatory.  If you do not find what you are looking for,* [contact us](https://reprex.nl/#contact) --- *we will try to put the data there from our repositories.*

### People & Diversity 

> The _Feasibility Study_ claims that “there is no real EU wide data on diversity in the music sector.  Diversity should include the study of ethnic minorities, gender and vulnerable groups...”

{{< figure library="true" src="/comparative/music_activity_playing_an_instrument_by_gender.png" title="Illusory data gap: active and music participation is available on EU level both for gender groups or four ethnic minorities – this is regularly featured in various European CAP surveys and in our national CAP surveys, too." >}}

However, active and music participation is available on EU level both for gender groups (see our chart) or four ethnic minorities – this is regularly featured in various European CAP surveys and in our national CAP surveys, too.  Our peer-reviewed, open-source [retroharmonize](https://retroharmonize.dataobservatory.eu/) statistical software was developed exactly to create these data products.

`Challenge Our Demo Observatory`: *Check out the* [Music, Society and Citizenship Pillar](https://data.music.dataobservatory.eu/music-society.html) *of our Demo Music Observatory.  If you do not find what you are looking for,* [contact us](https://dataobservatory.eu/#contact) --- *we will try to put the data there from our repositories.*

### Music Economy

Because music is mainly a market activity, apart from the mainly publicly funded classical (arts) music sector, and a part of the music (stage) infrastructure, a wide variety of data is available on the music economy in a consistent manner. 

We are calling on all partners to challenge us, either on Music Economy or the other pillars of the music observatory. We will try to provide the requested data on a weekly, monthly, quarterly or annually refreshing basis in the highest possible quality – for the first 50 request for free. We would like to demonstrate that most of the data gap is illusory, and a collaborative, bottom-up approach can deliver a European Music Observatory faster, cheaper in a much higher quality. 

`Challenge Our Demo Observatory`: *Check out the* [Music Economy Pillar](https://data.music.dataobservatory.eu/music-economy.html) *of our Demo Music Observatory.  If you do not find what you are looking for,* [contact us](https://dataobservatory.eu/#contact) --- *we will try to put the data there from our repositories.*

## Organization and institutional model {#organization}

We believe that the biggest shortcoming of the Feasibility Study is a systematic overview of a wide range of organizational possibilities.  The Feasibility Study is illustrated by examples from European Audiovisual Observatory as a good practice, investigates the possibility of integrating the music observatory into the EUIPO Observatory, and as an alternative, it considers the [six product observatories](https://ec.europa.eu/info/food-farming-fisheries/farming/facts-and-figures/markets/overviews/market-observatories_en) of DG Agriculture & Rural Development.  This approach provides a too narrow range of potential organizational alternatives.

We have reviewed a further 59 observatories, including ones that were not successful and ceased to exist, to understand why some observatories can increase their service level and why others fail. It is unclear what criteria make the European Audiovisual Observatory a good example, so it is impossible to say from this Feasibility Study if there are better examples – and we believe that there are.  The EAO is one of the oldest, if not the oldest observatories. It was created before the EU was founded before the commercial internet launched, when far different legal, governance and data collection needs had to be addressed. We believe that this may be the costliest and most time-consuming model to replicate.

### Bottom-up versus top-down

The Feasibility Study only considers hierarchical and centralized observatories, that operate on a top-down data integration, or rather, simple data collection strategy.  We have created a large observatory  with a very limited budget (which has a public layer, the Demo Music Observatory, and privately funded, much larger version, CEEMID) when we realized that the centralized, hierarchical, top-down approach is not suitable for a fragmented industry like the music industry. The example of CEEMID shows that a bottom-up and collaborative approach requires far less time, budget than a hierarchical approach, and can yield superior data quality. It is not surprising that most of the 62 observatories that we have studied are not hierarchical, and not operated by a centralized body but by a Consortium of various scientific, policy and industry stakeholders.

- [x] The `European Music Observatory` should fully exploit the EU's **open data** regime. (See our examples: [our first open data release](https://dataandlyrics.com/post/2020-04-16-regional-opendata-release/)) Our proposal about this were quoted in the _Feasibility Study_.

- [x] It should not re-collect data that already exists. Instead it should create policies, synergies and incentives that bring that data to light. The _Feasibility Study_ partly embraces this idea.

### Hierarchical versus decentralized observatory {#decentralization}

`We want big data to work for small venues, independent labels, startups, great and undiscovered artists.` We believe that you cannot make a successful album launch, a market entry or introduce a successful cultural policy without large amounts of well processed and correctly analysed data. We want to create a [Music Observatory](https://music.dataobservatory.eu/) that integrates the small data of many small bands, small labels, small venues, small countries, and mount correct the injustice. Make algorithms transparent and the competition fair.

- [x] It should not re-collect data that already exists. Instead it should create policies, synergies and incentives that bring that data to light. The _Feasibility Study_ partly embraces this idea.
- [ ] The observatory must allow a seamless [data integration](https://music.dataobservatory.eu/approach.html#dataintegration) between open data, and highly confidential proprietary data. The _Feasiblity Study_ wants to own and buy data, instead getting access to industry data.
- [ ] The open collaboration principle must allow an easy opt-in and opt-out for small and larger, public and private organizations, and offer for full transparency for all users. The _Feasibility Study_ offers a closed observatory without opt-in.

## Value For Money, Budget {#budget}

We believe that a bottom-up, collaborative approach of the industry stakeholders offers a much faster approach to growth, because it can mange conflicts of interests, build upon existing and trusted data assets.  The [annual budget](https://rm.coe.int/budget-19-information-income-and-expenses-of-the-european-audiovisual-/1680952994) of the European Audiovisual Observatory is about 3.7 million euros.  Most of the European data observatories that we surveyed have an annual budget of 20,000-200,000 euros. In our view, a very comprehensive data observatory can be built from 1-3 million euros and maintained with a collaborative use of existing data assets and a subsidy of up to 200,000 euros a year. 

## Quality Control {#quality}

- [x] It should be transparent, the indicator design should be based on open-source statistical software. Our proposal about this were quoted in the _Feasibility Study_.

- [ ] The European Music Observatory must embrace evidence-based [open Policy Analysis](https://music.dataobservatory.eu/approach.html#opa). This topic is not considered in the _Feasibility Study_.

## Use Cases {#use-cases}

We want to support the European music industry and our friends in North America, Australia, and all over the world to turn the tables with \@ref(innovation) [innovation](https://music.dataobservatory.eu/innovation.html) coming from the open source community.

* We want to help you to create alternative recommendation engines that actually recommend songs from your country, and we want to give you very clear export market targets with the help of [AI](https://music.dataobservatory.eu/innovation.html#ai). Our [Listen Local Initiative](https://dataandlyrics.com/project/listen-local/) is aiming to create recommendation engines for cities and regions, and make sure that local bands are recommended to local audiences and audiences in the regions where they will be touring after the Covid-19 pandemic. 

* We want your evidence to stand a fighting chance against large teams of professional legal and economics teams on the other side with [proper valuations and damage claims](https://music.dataobservatory.eu/innovation.html#valuation).  And we want to present all those hundreds and thousands of pages automatically, going through dozens and dozens of automated "unit-tests" until nobody can find errors.

* We want you to be able to prove to your fans, the press, your economy minister that music in many countries has not been at the mercy of the taxpayer, but has been carrying far heavier tax burdens than manufacturers.  We want to make your case that the music industry plays a vital role in the European economic recovery and job creation, because we can create [economic impact assessments](https://music.dataobservatory.eu/innovation.html#valuation#eia) on GDP, employment, tax, import and export effects automatically. 

* Because music and culture are often managed at the level of cities, regions and communities, we want to give you all the data on sub-national levels, whether for regions, metropolitan areas or smaller divisions.