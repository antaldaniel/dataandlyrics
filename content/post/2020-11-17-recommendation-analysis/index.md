+++
title = "Who Is Not Recommended On Spotify?"

date = 2020-11-17T11:03:00+02:00
lastmod = 2020-11-17T11:03:00+02:00
draft = false

authors = ["Daniel Antal"]

tags = ["listen-local", "big-data", "recommendations", "streaming", "spotify"]

summary = "You need to have 1000x more followers to double the routes leading to your artist profile and recordings with the current algorithms. We need new recommendation engines to dig out the local artists buried under a pile of international hits."

projects = ["listen-local"]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Left"

  # Show image only in page previews?
  preview_only = false

+++

*We are analysing how recommendations work for the artists involved in our [Listen Local](https://dataandlyrics.com/project/listen-local/) experiment. We created a testing database with their music and other artists from their cities, regions and countries. We need new recommendation engines to dig out from a pile of international hits the local artists.*

- [ ] Avoid landing on [Forgetify](https://dataandlyrics.com/post/2020-10-24-forgetify_pop_october/), in the universe of never listened-to-songs.
- [x] Understand how artists and their songs can find audience in the region relevant to their career goals, tour destinations, export opportunities.

Our preliminary analysis is not representative for nationality, though we believe that we will find serious regional, linguistic and national patterns. We are using examples from Spotify. To be fair to Spotify, while their algorithm has many problems, their API is at least very open, as opposed to Apple Music where we do not really know what is going on.

Our main concern is that some artists and their songs seem to be never recommended. Moreover, if artists and songs from a city, region or country are rarely or never recommended, then they risk losing their home market: the local audience will be recommended music that is coming outside of the city, region or country. 

{{< figure library="true" src="streaming/spotify_related_artists_corrplot_no_title.png" title="Artist has more related artists as number popularity and number of followers grows. Nationality may affect related artists." >}}

One of the most important way recommendations work is via `related artists`. If an artist has *no related artists*, it is very unlikely that either via user browsing interaction or via the algorithm that artists or her songs will be discovered by anybody.

*If you want *`your music and audience`* to be analysed in Listen Local, fill out* [this form](https://www.surveymonkey.com/r/ll_collector_2020)*. We will include you in our demo application and our analysis to be revealed in December.*

Because big data algorithms learn from user behaviour, more popular, more often selected songs, and songs selected by more users are more likely to be recommended.  

{{< figure library="true" src="streaming/spotify_related_artists_popularity.png" title="The algorithm can learn more about popular music, because the song is more often selected by a larger number of people" >}}

If the algorithm finds more related music, it means that it "learned" the repertoire of the artist. Artists with very little popularity tend to be related to 20-30 artists, but at a popularity level of 40-60 they are related to 30-40 artists. Seems simple, right?

Not that much. If you want the algorithm to learn your music well, you really have to go "viral".  

{{< figure library="true" src="streaming/spotify_related_artists_followers.png" title="Artist with less than 1000 followers risk not being to recommended at all. Doubling your chances to be discovered requires 1000x more followers." >}}

Doubling your routes to being recommended via other artists' music requires exponential growth.  You need to have `1000x` more followers to double the routes leading to your artist profile and recordings.

As we have shown, the current recommendation engines are re-enforcing the existing status quo, and they can [re-enforce the marginal status](https://dataandlyrics.com/post/2020-10-30-racist-algorithm/) of subcultures, artists from a nation, city or region. In other words, as we often say, `big data creates injustice`.

With our [Music Observatory](https://music.dataobservatory.eu/) for larger organizations and with our [Listen Local](https://dataandlyrics.com/project/listen-local/) analytics and recommendations for artists, managers and labels, we want to fight exactly this injustice. We are creating `transparent`, `open source`, and `responsible` tools and algorithms.