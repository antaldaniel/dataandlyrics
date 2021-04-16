+++
title = "Working With Localities and Location Tags"
substitle  = "Bandcamp Librarian — Part II"
date = 2021-04-13T09:00:00
lastmod = 2021-04-16T09:10:00
draft = false

authors = ["Botond Vitos"]

project = ["listen-local"]

tags = ["genres", "bandcamp", "mapping", "scenes"]

summary = "The second post in this series presents two use cases focused on localities and location tags (signifying cities, countries and sometimes nationalities). Such tags help putting local music scenes on the map; in the case of particularly prolific or creative cities they can be connected to specific genres too. Most commonly, they identify the city or country where the music label or the artist is based."

# Featured image
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Top"

  # Show image only in page previews?
  preview_only = false

+++

My [previous blogpost ](https://medium.com/data-lyrics/how-to-speak-about-music-in-the-digital-age-from-taxonomies-to-folksonomies-ac2d25ed29f7) addressed two ways of classifying music in the digital age: on the one hand, subgenre taxonomies proposed by industry vendors; on the other hand, user-defined collaborative tagging systems or folksonomies, which are more suitable for exploring niche music genres and to delve into the intricacies of an ever-evolving musical landscape. The Bandcamp Dance Librarian project takes into account both classification systems, using the taxonomy of industry vendor Beatport to detect stylistic tendencies or repertoires within the Bandcamp libraries of grassroots electronic dance music labels. This is performed by identifying clusters within a Bandcamp library based on Beatport’s subgenre labels. For instance, a cluster from the library of Samurai Music is identifed as an amalgam of Drum&Bass, Leftfield Bass, and to a lesser extent Trap-Hip-Hop-R&B. The dimension of this cluster (i.e., the number of tracks) is then displayed on a timeline among other clusters.

Bandcamp is a reputable publishing platform aimed towards independent musicians that encourages the use of tags (folksonomies) by its users — accordingly, the Librarian takes into account the artist/label tags added to the Bandcamp pages. It is therefore possible to compare the industry taxonomy of Beatport with artist folksonomies, as long as such tags are provided on Bandcamp or further investigation around particular folksonomies is performed. For instance, a representative track from the cluster identified above is described, among others, as “homemade weaponry” by the eponymous artist:

{{< figure src="/img/bandcamp_librarian/homemade_weaponry.jpg" title="homemade weaponry" numbered="true" >}}

Bandcamp link: [https://homemadeweapons.bandcamp.com/track/hawkeye](https://homemadeweapons.bandcamp.com/track/hawkeye)

A few more (technical) details about the project: The classifier is based on the methodology of Caparrini et al. (2020), using 92 audio features extracted from electronic dance music tracks within Beatport’s Top-100 lists in various subgenres. Bandcamp offers freely available full-length (low-bitrate) streams as track previews, which are suitable for musical feature extraction and analysis. Complete Bandcamp libraries are processed, and each track’s class (subgenre) probabilities are determined by the classifier, which forms the basis for the clustering algorithm. The number of clusters can be set in advance or calculated automatically. Results are provided in a PDF file with links to up to three representative Bandcamp tracks (if possible, from different artists) in each group and their attached tags (folksonomies).

The remainder of this post presents two use cases focused on localities and location tags (signifying cities, countries and sometimes nationalities). Such tags help putting local music scenes on the map; in the case of particularly prolific or creative cities they can be connected to specific genres too. Most commonly, they identify the city or country where the music label or the artist is based. Electronic music production requires relatively accessible tools and is usually carried out entirely by the producer; prominent artists are often running record labels that are integral to promoting music and structuring scenes. These aspects contribute to the burgeoning of independent music communities across the globe.

Our first example draws on features extracted from 36 Bandcamp label libraries. The libraries are taken from a piece of music journalism ([https://cdm.link/2020/05/underground-techno-labels-a-bandcamp-guide/](https://cdm.link/2020/05/underground-techno-labels-a-bandcamp-guide/)) addressing some of Bandcamp’s “underground” techno labels that “have a sense of community, even [as] a small collective of a few friends unlikely to catch larger attention”. Such specialist music press is characterized by Canadian sociologist Sarah Thorton as _niche media_, which is particularly efficient in categorizing social groups, classifying sounds, defining cultural distinctions and baptizing genres. The list of labels offered in the CDM article is suitable for our current aim: a blink into the sound of “underground” techno labels based on their Bandcamp location tags.

The collection includes 14.200 tracks analyzed by the Librarian. A total of 97.334 tags are attached to the tracks, as illustrated by the word cloud below:

{{< figure src="/img/bandcamp_librarian/image_2_tags.png" title="A total of 97.334 tags are attached to the tracks" numbered="true" >}}

In total, 12000 tags refer to locations or nationalities. The majority of the location tags designate cities — more often than not, these are where the labels are based:

{{< figure src="/img/bandcamp_librarian/image3_location_tags.png" title="Location Tags" numbered="true" >}}

The following table shows the total number of tags pertaining to each location (city), and the number of labels that tagged these cities at least once within their Bandcamp library:

{{< figure src="/img/bandcamp_librarian/tags_per_city.jpg" title="Tags per city" numbered="true" >}}


(Note: United Kingdom has been conflated with London for the purposes of this illustration.)

In one way or another, the relative relevance of these cities within the global techno circuit can be inferred from these numbers.

By instructing the Librarian to treat as a single cluster all tracks that are tagged with the same city label, an attempt can be made to delineate an overall — although not the only — sound that can be comfortably identified with a location. Berlin, for instance, can be classified as follows:

{{< figure src="/img/bandcamp_librarian/berlin_classification.jpg" title="Berlin Classification" numbered="true" >}}

Bandcamp links:

- [https://pacou.bandcamp.com/track/dancer](https://pacou.bandcamp.com/track/dancer)
- [https://flashrec.bandcamp.com/track/anml-mthr-alarm](https://flashrec.bandcamp.com/track/anml-mthr-alarm)
- [https://ostgut.bandcamp.com/track/scenario](https://ostgut.bandcamp.com/track/scenario)

The UK is another noteworthy example:

{{< figure src="/img/bandcamp_librarian/uk_classification.jpg" title="United Kingdom Classification" numbered="true" >}}

Bandcamp links:

- [https://perctrax.bandcamp.com/track/zelo-radial-remix](https://perctrax.bandcamp.com/track/zelo-radial-remix)

- [https://perctrax.bandcamp.com/track/ganymede-perc-dub-mix](https://perctrax.bandcamp.com/track/ganymede-perc-dub-mix)

- [https://planetaryassaultsystems.bandcamp.com/track/om-the-def](https://planetaryassaultsystems.bandcamp.com/track/om-the-def)

Of course, defining a single cluster will not account for the sonic variety of such influential cities.

As expected, the detected subgenres are concentrated on the various flavours of techno. For more stylistic variety, we can use the Librarian with different music styles and datasets. The following example concerns artists that could be affiliated with the [Listen Local initiative](http://listenlocal.community/). Our goal was to focus on Slovakian artists on Spotify that have Bandcamp presence too, and use the Librarian as support for the recommendations. A sample of 82 such artists was selected; their Bandcamp libraries included 2379 tracks. In total, 17.881 tags were attached to these tracks, among which 550 were unique. The tag frequencies are illustrated below:

{{< figure src="/img/bandcamp_librarian/tag_frequencies.jpg" title="Tag Frequencies" numbered="true" >}}

As the word cloud also suggests, the tracks cover a variety of genres. Accordingly, our classifier should be more general in scope than in the case of the techno labels. A suitable option is the MSD-MusiCNN TensorFlow auto-tagging model supplied with the Essentia library [https://mtg.github.io/essentia-labs/news/tensorflow/2020/01/16/tensorflow-models-released/](https://mtg.github.io/essentia-labs/news/tensorflow/2020/01/16/tensorflow-models-released/), which predicts LastFm’s top-50 music classification tags (a selection of 24 tags referring to music genres or styles were predicted for the purposes of this demonstration).

One can get a first feel of the stylistic tendencies within the sample by looking at the classification tags with the highest mean probability values:

- rock 0.169777

- Hip-Hop 0.141943

- electronic 0.136527

- alternative 0.079971

- pop 0.066009

Accordingly, the five most representative genres or styles in our collection are rock, hip-hop, electronic, alternative and pop.

A more refined perspective is gained after clustering the tracks based on their tag probability values. The algorithm proposes three clusters by default, crystallized around the rock (alternative/pop), hip-hop, and electronic (ambient/dance) genres:

{{< figure src="/img/bandcamp_librarian/Listen_Local_Clusters.jpg" title="Listen Local Clusters" numbered="true" >}}

Bandcamp links:

- [https://papyllon.bandcamp.com/track/never-felt-so-pure](https://papyllon.bandcamp.com/track/never-felt-so-pure)

- [https://ills.bandcamp.com/track/laugh-will-tear-us-apart](https://ills.bandcamp.com/track/laugh-will-tear-us-apart)

- [https://theswanbride.bandcamp.com/track/styx-travel-inc](https://theswanbride.bandcamp.com/track/styx-travel-inc)


{{< figure src="/img/bandcamp_librarian/sk_hiphop_cluster.jpg" title="Hip-hop Cluster" numbered="true" >}}

Bandcamp links:

- [https://piosquad.bandcamp.com/track/worldwide-feat-heltah-skeltah](https://piosquad.bandcamp.com/track/worldwide-feat-heltah-skeltah)

- [https://nirobaits.bandcamp.com/track/awesome-ft-candy-mane-otecko-and-mr-sulo](https://nirobaits.bandcamp.com/track/awesome-ft-candy-mane-otecko-and-mr-sulo)

- [https://everydays.bandcamp.com/track/mal-m-sto-feat-sinuz-prod-by-sinuz](https://everydays.bandcamp.com/track/mal-m-sto-feat-sinuz-prod-by-sinuz)


{{< figure src="/img/bandcamp_librarian/sk_electronic_cluster.jpg" title="Electronic (ambient/dance) Cluster" numbered="true" >}}

Bandcamp links:

- [https://kurkus.bandcamp.com/track/interstellar](https://kurkus.bandcamp.com/track/interstellar)

- [https://nightlines.bandcamp.com/track/udia-istoty](https://nightlines.bandcamp.com/track/udia-istoty)

- [https://noreligionlabel.bandcamp.com/track/go-outside-outro](https://noreligionlabel.bandcamp.com/track/go-outside-outro)

The track examples provide the closest matches with the identified subgenres, and the complete clusters are not restricted to these styles. However, by increasing the cluster number it is possible to further refine the results. By increasing it to five groups, for example, a rock/electronic/pop fusion group is also identified, and metal appears as a new determining genre:

{{< figure src="/img/bandcamp_librarian/rock_electronic_pop_fusion_group.jpg" title="Rock/Electronic/Pop fusion group Cluster" numbered="true" >}}


Bandcamp links:

- [https://monikinokino.bandcamp.com/track/be-ky-radio-edit](https://monikinokino.bandcamp.com/track/be-ky-radio-edit)

- [https://midilidi.bandcamp.com/track/koupali-t-tajemn](https://midilidi.bandcamp.com/track/koupali-t-tajemn)

- [https://denaftb.bandcamp.com/track/if-its-written-outro](https://denaftb.bandcamp.com/track/if-its-written-outro)

{{< figure src="/img/bandcamp_librarian/metal_group.jpg" title="Metal Cluster" numbered="true" >}}

Bandcamp links:

- [https://triggerband.bandcamp.com/track/treachery](https://triggerband.bandcamp.com/track/treachery)

- [https://signumregis.bandcamp.com/track/unfold-the-mystery](https://signumregis.bandcamp.com/track/unfold-the-mystery)

- [https://hudba.zocivoci.sk/track/prehra-a-zmizn](https://hudba.zocivoci.sk/track/prehra-a-zmizn)

If you’d like to have a look at these and other stylistic groups (or search based on location tags), a working demo of the Librarian loaded with the Listen Local dataset is available at: [bitly.com/bandcamp-librarian](https://bitly.com/bandcamp-librarian). Happy discoveries!

## References

Alonso-Jiménez, Pablo, Dmitry Bogdanov, Jordi Pons and Xavier Serra. 2020. TensorFlow Audio Models in Essentia. arXiv:2003.07393.

Besseny, Amelia. 2020. Lost in spotify: folksonomy and wayfinding functions in spotify’s interface and companion apps. _Popular Communication_. no. 18 (1): 1–17.

Caparrini, Antonio, Javier Arroyo, Laura Pérez-Molina and Jaime Sánchez-Hernández. 2020. “Automatic subgenre classification in an electronic dance music taxonomy.” Journal of New Music Research 49(12):1–16.

Charles, Christopher. 2019. “Part of the Tribe: Crews, Residence, and Affiliation in Underground Dance Music Scenes”. IASPM Journal, no. (9) 2: 55–74.

Thornton, Sarah. 1996. _Club Cultures: Music, Media, and Subcultural Capital_. Hanover: University Press of New England.
