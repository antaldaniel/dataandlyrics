+++
title = "Why Did We Start The Demo Music Observatory?"

date = 2020-10-27T10:00:00+02:00
lastmod = 2020-10-27T10:00:00+02:00
draft = false

authors = ["Daniel Antal, CFA"]

tags = ["musicology", "recommendations", "machine-learning", "playlist", "listen-local", "forgetify"]

summary = "Forgetify is an application that is “recommending” you songs that have never been played on Spotify - not even by their families, friends or foes. When you design a recommendation engine for an artist or a label, you want to avoid that their songs ever arrive to Forgetify."

projects = ["listen-local", "music-observatory"]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "Comparing the living standards of musicians and the general population"

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Center"

  # Show image only in page previews?
  preview_only = false

+++

I was contacted during the consultation period of the Feasibility Study of the European Music Observatory. That led to an uneasy series of conversations with the consultants of this project, and a very enlightening series of conversations with European civil servants, music industry organizations, music managers and artists.  My main pitch was that every single assumption of this project is wrong.

They started from the assumption that there is hardly any data available on the European music scene -- whereas we found while building up CEEMID, errr, a pan-European music data observatory, is that music is one of the most data-driven industries in the world, it is choking in numbers, and the reason why this data is not visible is very different. They were talking about lack of data in fields where we already had about 2000 pan-European indicators ready. (See [Introducing the CEEMID Observatory, 9/28/2019](https://danielantal.eu/presentation/ceemid-observatory.html#/) *large self-contained html file, takes time to load into browser*)

## Big data creates injustice

The music industry is scattered: it has the author’s or publishing side, the recording side, a large live music business and usually a very environment for classical (art) music. Within these segments there are hundreds of organizations in each EU country, and each have their own small or large datasets. The music industry has plenty of data, but it is not integrated, and it is often hidden from organizations that may have a conflicting agenda.  

<img src="three_income_streams_croatia.png" width="90%" alt="Fragmentation: Three income streams in Croatia" title="Fragmentation: Three income streams in Croatia" />

The fragmentation of data makes these players easy prey in the era of big data. Companies who monopolise big datasets first and create [weapons of math destruction](https://blogs.scientificamerican.com/roots-of-unity/review-weapons-of-math-destruction/) in the forms of algorithms that work for them, can take an unusually large share of the money created throughout the value chain. Proprietary, uncontrolled, big data trained algorithms reinforce inequality --- this makes Google’s YouTube, Spotify, but also Netflix in films or Amazon in books so powerful against its competitors, but also against competition regulators or suppliers --- in this case songwriters, video producers, filmmakers, book publishers and authors.  If their algorithm works against a creator, the creator is doomed, because half of the global sales are driven by secret algorithms.

## From hierarchical planning to open collaboration

Scattered industries tend to be riddled with conflicts of interests.  While working with royalty collection management societies in the last 7 years I often saw that songwriters, producers and performers are often fighting each other for slices of the pie that is just too small. That means that national members of CISAC (GESAC in Europe), IFPI, and AEPO-ARTIS often do not share data with each other, although their income is below any legally acceptable threshold. They have individually very rich datasets that in many jurisdictions just never meet. Labels, small publishers are so little organizations that they do not have a data scientist, let alone a dedicated IT person, or even an HR professional to hire the services of data scientists.

We were able to collect at least 70% of the information content of the planned European Music Observatory, and far more, than most of the 50 data observatories we examined in Europe, because we took an approach inspired in open source software development: continuous opt-in, opt-out data integration, focusing on the synergies that partners can achieve, instead of aiming at endless discussions and compromises on sharing data. We never take away proprietary data from anybody, we just connect data among partners, and enrich it with open data.

## Big data vs much small data, research automation

Most music organization employ 1-5 people, and even the largest national organization, like collective management organizations, fall under the EU definition of *small- and medium sized enterprises*. They do not have data scientists, market researchers, forecasters.  They are small organizations with small research budgets and very little time for researching. 

[x] We automated most of the research tasks, to make it less costly, less error-prone, and require less labour input.  We can automate most of the data collection, data processing, imputation, validation, documentation, reporting, even some modeling.

[x] We invested into harvesting the vast open data of the European Union and its member states.  In the EU, most taxpayer funded research data is freely available, but at a cost of significant data reprocessing cost. If the data was originally collected to calcualte to inflation or monitor tax revenues, it needs to be significantly altered for the music industry to be useful.

[x] We automated the connection of many small data sources and open data. We can create big data from much small data, and deploy analytics, algorithms on collective datasets.

<img src="digital_gap_2018.jpg" width="90%" alt="Difference between potential market (household cultural spending) and actual digital music revenues" title="Closing the royalty gap in Europe" />

