---
title       : BOTANICAL CLOCK
subtitle    : by Carolus Linnaeus
author      : Urli2016
job         : Reproducible Presentation
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

##### BOTANICAL CLOCK, GENERAL INFORMATION, Slide 1

```r
library(shiny)
```

```
## Warning: package 'shiny' was built under R version 3.2.4
```

```r
library(ggplot2)
```

```
## Warning: package 'ggplot2' was built under R version 3.2.5
```

```r
library(knitr)
```

```
## Warning: package 'knitr' was built under R version 3.2.5
```

```r
library(markdown)
Flowers <- read.csv("Flowers.csv")
```

###### Carolus Linnaeus has been an awarded scientist in the 17th century and he had the hypothetical plan to plant a clock ruled by the opening and closing times of different flowers. He had a list by his own, I only took a few and created my own csv-file called 'Flowers.csv' ordered by opening times.

---

##### BOTANICAL CLOCK, DESCRIPTION, Slide 2
###### I decided to use a ShinyUI(navbarPage) as it has not been used in the class. One of our tasks was to implement a widget. I created a selectbox in order to show the botanical names of these flowers in latin and therefore recognizable by scientists all over the world. I also added a Markdown-File including the biography of Carolus Linnaeus and a rough description of the flowers.


```r
shinyUI(navbarPage("BOTANICAL CLOCK",
                   tabPanel("Description",
                            sidebarLayout(
                                 sidebarPanel(
                                 selectInput("select", label = h3("Botanical Names of Flowers"),                                                                         choices = list("Yellow Goats Beard" = "Tragopogon pratensis", "Rough Hawkbit" = "Leontodon hispidus", "Narrow Leaf Hawksbeard" = "Crepis tectorum", "Sow Thistle" = "Sonchus oleraceus", "Dandelion" = "Taraxacum officinale Weber", "Hawksbeard" = "Crepis alpina", "False Sow Thistle" = "Reichardia tingitana", "Spotted Cats Ear" = "Hypochaeris maculata", "Canadian Hawkweed" = "Hieracium umbellatum", "Marsh Sow Thistle" = "Sonchus palustris", "Blue Sow Thistle" = "Cicerbita alpina", "Garden Lettuce" = "Lactuca sativa", "White Waterlily" = "Nymphaea alba", "Scarlet Pimpernel" = "Anagallis arvensis", "Ice Plant" = "Mesembryanthemum crystallinum", "Quill FameFlower" = "Phemerantus teretifolius", "Sundrops" = "Oenothera fruticosa")),
                                     hr(),
                                     fluidRow(column(10, verbatimTextOutput("value"))
                                 )
                                 ),
                                 mainPanel(
                                        includeMarkdown("Description.md"))
                                 ))))
```

<!--html_preserve--><nav class="navbar navbar-default navbar-static-top" role="navigation">
<div class="container">
<div class="navbar-header">
<span class="navbar-brand">BOTANICAL CLOCK</span>
</div>
<ul class="nav navbar-nav">
<li class="active">
<a href="#tab-5239-1" data-toggle="tab" data-value="Description">Description</a>
</li>
</ul>
</div>
</nav>
<div class="container-fluid">
<div class="tab-content">
<div class="tab-pane active" data-value="Description" id="tab-5239-1">
<div class="row">
<div class="col-sm-4">
<form class="well">
<div class="form-group shiny-input-container">
<label class="control-label" for="select">
<h3>Botanical Names of Flowers</h3>
</label>
<div>
<select id="select"><option value="Tragopogon pratensis" selected>Yellow Goats Beard</option>
<option value="Leontodon hispidus">Rough Hawkbit</option>
<option value="Crepis tectorum">Narrow Leaf Hawksbeard</option>
<option value="Sonchus oleraceus">Sow Thistle</option>
<option value="Taraxacum officinale Weber">Dandelion</option>
<option value="Crepis alpina">Hawksbeard</option>
<option value="Reichardia tingitana">False Sow Thistle</option>
<option value="Hypochaeris maculata">Spotted Cats Ear</option>
<option value="Hieracium umbellatum">Canadian Hawkweed</option>
<option value="Sonchus palustris">Marsh Sow Thistle</option>
<option value="Cicerbita alpina">Blue Sow Thistle</option>
<option value="Lactuca sativa">Garden Lettuce</option>
<option value="Nymphaea alba">White Waterlily</option>
<option value="Anagallis arvensis">Scarlet Pimpernel</option>
<option value="Mesembryanthemum crystallinum">Ice Plant</option>
<option value="Phemerantus teretifolius">Quill FameFlower</option>
<option value="Oenothera fruticosa">Sundrops</option></select>
<script type="application/json" data-for="select" data-nonempty="">{}</script>
</div>
</div>
<hr/>
<div class="row">
<div class="col-sm-10">
<pre id="value" class="shiny-text-output"></pre>
</div>
</div>
</form>
</div>
<div class="col-sm-8"><h3>CAROLUS LINNAEUS - 1707-1778</h3>

<h4>Linnaeus was born in Southern Sweden, at the countryside of Smaeland. He received most of his education at Uppsala University, and began giving lectures in botany at Uppsala University in 1730. He lived abroad between 1735 and 1738, where he studied and also published a first edition of his Systema Naturae (lit. = natural system) in the Netherlands. He returned to Sweden, where he became professor of medicine and botany at Uppsala University. In the 1740s, he was sent on several journeys through Sweden to find and classify plants and animals. In the 1750s and 1760s, he continued to collect and classify animals, plants, and minerals, and published several volumes. At the time of his death, he was one of the most acclaimed scientists in Europe.</h4>

<h3>The idea behind</h3>

<h4>The idea of a botanical or flower clock has not been new by that time. Some 30 years before Andrew Marvel described in his poem &ldquo;The Garden&rdquo; maybe already a botanical clock in 1678:</h4>

<h4>How well the skilful gardener drew</h4>

<h4>Of flow&#39;rs and herbs this dial new;</h4>

<h4>Where from above the milder sun</h4>

<h4>Does through a fragrant zodiac run;</h4>

<h4>And, as it works, th&#39; industrious bee</h4>

<h4>Computes its time as well as we.</h4>

<h4>How could such sweet and wholesome hours</h4>

<h4>Be reckoned but with herbs and flow&#39;rs!</h4>

<h4>Linnaeus botanical or flower clock was a hypothesized garden plan that would take advantage of several plants that open or close their flowers at particular times of the day to accurately indicate the time. He proposed the concept in his 1751 publication Philosophia Botanica, calling it the Horologium Florae=flower clock. He may never have planted such a garden, but the idea was attempted by several botanical gardens in the early 19th century, with mixed success. Many plants exhibit a strong circadian rhythm (see also Chronobiology), and a few have been observed to open at quite a regular time, but the accuracy of such a clock is diminished because flowering time is affected by weather and seasonal effects plus Linnaeus&#39; flower clock ends at 9:00 pm.</h4>

<h3>Flowers of Botanical Clock as shown in my plot, short description, sorted by Opening Time:</h3>

<h4>Yellow Goats Beard, botanical name: Tragopogon pratensis, Opening Time: 3:00 am, Closing Time: 12:00 pm</h4>

<h5>This aster-family weed and biennial plant is a low-growing rosette during the first year. Each stem is round, hairless, and often somewhat enlarged at the base of each leaf. The cauline leaves alternate sparingly and become smaller as they ascend the stems. The adventive Yellow Goat&#39;s Beard is common in central and northern Illinois, but occasional or absent in the southern section of the state. It is native to Eurasia. Habitats include mesic black soil prairies, weedy meadows near woodlands, areas along roads and railroads, vacant lots, and miscellaneous waste areas. Disturbed areas are preferred, although this plant can be found occasionally in prairie remnants along railroads.</h5>

<h4>Rough Hawkbit, botanical name: Leontodon hispidus, Opening Time: 4:00 am, Closing Time: 5:00 pm</h4>

<h5>Rough hawkbit is a short, grassland perennial with a very hairy stem that swells slightly at the top. The solitary flowers, which are in bloom from late May to October, are a rich golden yellow with the outer florets often reddish or orange and the bracts behind the flower appearing very shaggy. The leaves which make up the basal rosette are long and bluntly lobed.</h5>

<h4>Narrow Leaf Hakwsbeard, botanical name: Crepis tectorum, Opening Time: 4:00 am, Closing Time: 12:00 pm</h4>

<h5>Narrowleaf hawksbeards original stand in Finland is native to nutritious rocky outcrops, bird rocks and meadows, but the alien stand which thrives close to people is much more common. It probably originally became common through cereal cultivation, it can still be seen now and then growing in fields as a weed, but it is more common in fallow fields and beside roads. In particular it thrives around inhabited areas which people have made more fertile. In an urban environment the species has made use of open, dry places in railway yards, industrial and storage areas, waste ground and cracks in the pavement. It used to even grow on lichenous turf and shingle roofs. Narrowleaf hawksbeards capitula open soon after sunrise but they close before noon.</h5>

<h4>Sow Thistle, botanical name: Sonchus oleraceus, Opening Time: 5:00 am, Closing Time: 12:00 pm</h4>

<h5>The Sow Thistle is a well known weed in every field and garden. It is a perennial, growing from 1 to 3 feet high, with hollow thick, branched stems full of milky juice, and thin, oblong leaves, more or less cut into with irregular, prickly teeth on the margins. The upper leaves are much simpler in form than the lower ones, clasping the stem at their bases. The flowers are a pale yellow, and when withered, the involucres close over them in a conical form. The seed vessels are crowned with a tuft of hairs, or pappus, like most of this large family of Compositae. This plant is subject to great variations, which are merely owing to soil and situation, some being more prickly than others.</h5>

<h4>Dandelion, botanical name: Taraxacum officinale Weber, Opening Time: 5:00 am, Closing Time: 9:00 am</h4>

<h5>The Dandelion though not occurring in the Southern Hemisphere, is at home in all parts of the north temperate zone, in pastures, meadows and on waste ground, and is so plentiful that farmers everywhere find it a troublesome weed, for though its flowers are more conspicuous in the earlier months of the summer, it may be found in bloom, and consequently also prolifically dispersing its seeds, almost throughout the year. From its thick tap root, dark brown, almost black on the outside though white and milky within, the long jagged leaves rise directly, radiating from it to form a rosette Iying close upon the ground.</h5>

<h4>Hawksbeard, botanical name: Crepis alpina, Opening Time: 5:00 am, Closing Time: 11:00 am</h4>

<h5>Crepis, commonly known in some parts of the world as hawksbeard or hawks-beard (but not to be confused with the related genus Hieracium with a similar common name), is a genus of annual and perennial flowering plants of the family Asteraceae superficially resembling the dandelion, the most conspicuous difference being that Crepis usually has branching scapes with multiple heads (though solitary heads can occur). The genus name Crepis derives from the greek word &ldquo;krepis&rdquo;, meaning &ldquo;slipper&rdquo; or &ldquo;sandal&rdquo;, possibly in reference to the shape of the fruit. It is distributed throughout the Norther Hemisphere and Africa and several plants are known as introduced species worldwide. The center of diversity is in the Mediterranean.</h5>

<h4>False Sow Thistle, botanical name: Reichardia tingitana, Opening Time: 6:00 am, Closing Time 10:00 am</h4>

<h5>False Sow Thistle belongs to a group of mainly yellow-flowered daisies in the Tribe Lactuceae. The plants in this tribe are characterised by having a basal rosette of leaves (flat weeds), milky sap in their stems and their flower-heads consisting entirely of ray florets (for example: no eye to the daisy). It is an annual to perennial tap-rooted herb with fleshy and hairless leaves with minutely prickly margins. Basal leaves oblanceolate (lance shaped with the narrowend attached to the stem). The flowers are yellow with a purplish base and the outer petals red-striped. Their habitat is scattered on coastal sand dunes and on sandy soils in the far north-west of Victoria.</h5>

<h4>Spotted Cats Ear, botanical name: Hypochaeris maculata, Opening Time: 6:00 am, Closing Time: 5:00 pm</h4>

<h5>Spotted Cats ears large capitula make it a very attractive and eye-catching ornamental plant. In bygone times the appearance of its yellow capitula on meadows meant the beginning of hay-work in agricultural communities. Apart from being a calendar plant, Spotted Cats Ear also served as a clock: hay-work began at 6:00 am, the same time as the plant opens its capitulum ??? and it was time to return home for dinner when it closed up again at 5:00 pm. Nowadays of course an adjustment must be made for summer time, which is an hour ahead. Spotted cat???s ear has been useful in more concrete ways too: the leaf can be boiled like cabbage and the roots and capitulum make a good general tonic.</h5>

<h4>Canadian Hawkweed, botanical name: Hieracium umbellatum, Opening Time: 6:00 am, Closing Time: 5:00 pm</h4>

<h5>Canadadian Hawkweed is an erect native perennial growing to 5 inches in height on stems that are smooth and unbranched below the inflorescence. Within the inflorescence the stem is green to greenish-red and is rough. Stems contain a milky juice. The leaves are alternate and located on the stem below the inflorescence. They are lanceolate to elliptical, stalkless; tips are pointed. The margins usually have small sharply pointed teeth, but irregularly spaced, sometimes giving the appearance of small lobes. The upper surface is a greenish gray, smooth, while the lower surface can be hairy and rough. Leaf edges do not have hair. Canada Hawkweed and related species grow in dry areas of woods, thickets, prairies, in more sandy type soils with mesic to dry moisture conditions, in full sun.</h5>

<h4>Marsh Sow Thistle, botanical name: Sonchus palustris, Opening Time: 7:00 am, Closing Time: 12:00 pm</h4>

<h5>The Marsh Sow-Thistle is a much taller species than either of the preceding, attaining a height of 6 to 8 feet, being one of the tallest of our English herbaceous plants. The root is perennial, fleshy and branched, but not creeping; the leaves, arrow-shaped at the base, large, shiny on the under surfaces; the flowers, large and pale yellow, with hairy involucres, are in bloom in September and October, much later than the last species, which it somewhat resembles, though the edges of the leaves are minutely toothed, not waved. It grows in marshy places but is rare in this country, being now extinct in most of the places in Norfolk, Suffolk, Kent and Essex where it was formerly found, and only occurring on the Thames below Woolwich. This thistle was placed by mediaeval botanists under the planetary influences of Mars: &#39;Mars rules it, it is such a prickly business.&#39;</h5>

<h4>Blue Sow Thistle, botanical name: Cicerbita alpina, Opening Time: 7:00 am, Closing Time: 12:00 pm</h4>

<h5>Cicerbita alpina, commonly known as the Alpine Sow-thistle or Alpine Blue-sow-thistle is a perennial herbaceous plant sometimes placed in the genus Cicerbita of the Asteraceae family and sometimes place in the genus Lactuca as Lactuca alpina. Cicerbita alpina grows on many mountains of Europe (for example: the Apls, the Pyrenees, the northern Apennines, the Scandinavian Peninsula, Scotland, the Carpathians, Romania and the Urals.These plants can be found in alpine woods, besides streams, in rich-soil in hollows and in tall meadows, usually between 1,000 and 1,800 metres (3,300 and 5,900 ft) above sea level.</h5>

<h4>Garden Lettuce, botanical name: Lactuca sativa, Opening Time: 7:00 am, Closing Time: 10:00 am</h4>

<h5>Lettuce is an annual plant of the daisy family Asteraceae. It is most often grown as a leaf vegetable, but sometimes for its stem and seeds. Lettuce was first cultivated by the ancient Egyptians who turned it from a weed, whose seeds were used to produce oil, into a food plant grown for its succulent leaves, in addition to its oil-rich seeds. Lettuce spread to the Greeks and Romans, the latter of whom gave it the name lactuca from which the English lettuce is ultimately derived. By 50 AD, multiple types were described, and lettuce appeared often in medieval writings, including several herbals.Europe and North America originally dominated the market for lettuce, but by the late 20th century the consumption of lettuce had spread throughout the world.</h5>

<h4>White Waterlily, botanical name: Nymphaea alba, Opening Time: 7:00 am, Closing Time: 5:00 pm</h4>

<h5>Nymphaea alba, also known as the European white water-lily, white water rose or white nenuphar, is an aquatic flowering plant of the family Nymphaecaeae. It grows in water that is 30 to 50 cm (12 to 9 in) deep and likes large ponds and lakes. The leaves can be up to 30 cm (12 inches) in diameter and they take up a spread of 150 cm (59 in) per plant. The flowers are white and they have many small stamens inside. It is found all over Europe and in parts of North Africa and the Middle East in freshwater. The red variety (Nymphaea alba f. rosea) which is in cultivation came from lake Fair Tarn in the forest of Tiveden, Sweden, where they were discovered in the early 19th century. The discovery led to a large scale exploitation which nearly made it extinct in the wild before it was protected.</h5>

<h4>Scarlet Pimpernel, botanical name: Anagallis arvensis, Opening Time: 8:00 am, Closing Time: 5:00 pm</h4>

<h5>Scarlet pimpernel (Anagallis arvensis; also known as red pimpernel, red chickweed, poorman&#39;s barometer, poor mans weather-glass, shepherds weather glass or shepherds clock because it flowers from 8 am to 4-5 pm) is a low-growing annual plant. The native range of the species is Europe and Western Asia and North Africa. The species has been distributed widely by humans, either deliberately as an ornamental flower or accidentally. A. arvensis is now naturalised almost worldwide. This common european plant is generally considered a weed and is an indicator of light soils, though it grows opportunistically in clavey soils as well.</h5>

<h4>Ice Plant, botanical name: Mesembryanthemum crystallinum, Opening Time: 9:00 am, Closing Time: 9:00 pm</h4>

<h5>The ice plant is a prostrate succulent plant native to Africa, Sinai and Southern Europe and naturalized in North America, South America and Australia. The plant is covered with large, glistening bladder cells or water vesicles, reflected in its common names of common iceplant, crystalline iceplant or ice plant. It can be annual, biennial or perennial, but its life cycle is usually completed within several months, depending on environmental conditions. It is found on a wide range of soil types, from well-drained sandy soils (including sand dunes), to loamy and clay soils. It can tolerate nutritionally poor or saline soils. As with many introduced species it also grows in disturbed sites such as roadsides, rubbish dumps and homestead yards. The ice-plant flowers from spring to early summer. Flowers open in the morning and close at night and are insect pollinated.</h5>

<h4>Quill Fameflower, botanical name: Phemerantur teretifolius, Opening Time: 3:00 pm, Closing Time: 7:00 pm</h4>

<h5>Quill fameflower is a member of the Portulacaceae, the Purslane family. This family includes spring beauty, montia, and the weedy introduced purslane among others. Many of the species in the family are succulent or fleshy, adapted for arid or saline environments. In older manuals, this species is called Talinum teretifolium Pursh. Sixteen species of fameflower are recognized in North America, most from the southwest or plains states. Phemeranthus means ephemeral flower in reference to the short life of each flower.The flowers open about 3 pm EDT and close before sunset, lasting only one day. A single large plant may produce one hundred or so flowers.</h5>

<h4>Sundrops, botanical name: Oenothera fruticosa, Opening Time: 6:00 pm, Closing Time: 4:00 am</h4>

<h5>Oenothera fruticosa, commonly called sundrops or southern sundrop, is an erect, day-flowering member of the evening primrose family. This native typically grows 15-30??? tall and produces terminal clusters of bright yellow four-petaled flowers on stems clad with lanceolate green leaves. Flowers are followed by distinctive club-shaped seed capsules. Each flower is short-lived, but flowers bloom in succession over a fairly long period of two months. The beauty of this variety is its evergreen reddish color in winter.</h5>
</div>
</div>
</div>
</div>
</div><!--/html_preserve-->

---

##### BOTANICAL CLOCK, PLOT, Slide 3
###### Vizualization of the Opening and Closing Times of the flowers in alphabetical order. The code had to be wrapped in the command print() on the Shiny server side.


```r
ggplot(data=Flowers, aes(x=CLOSING,y=OPENING,fill=FLOWER)) +
                geom_bar(position="dodge",stat="identity") +
                ggtitle("Botanical Clock")
```

![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3-1.png)

---

##### BOTANICAL CLOCK, EVEN MORE, Slide 4
###### Nowadays botanical or flower clocks look totally different. In fact these are planted large decorative clocks with the clock face formed by carpet bedding, usually found in a park or other public recreation area. I embedded another Markdown-File called 'More.md' as follows:


```r
tabPanel("More",
              mainPanel(
                      fluidRow(
                              column(10,
                                     includeMarkdown("More.md")))))
```

---

#### BOTANICAL CLOCK, PICTURE OF A CURRENT FLOWER CLOCK, Slide 5
###### As the cherry of the pie I finally wanted to show a picture of how a botanical or flower clock looks like nowadays and I added one of Germany as I am a german. Please find all related files hosted in my github repository 'https://github.com/Urli2016/GitHub/tree/master/BotanicalCl_A/BotanicalClockA/BotanicalClockA'.


```r
img(class="img-polaroid",
      src=paste0("http://upload.wikimedia.org/",
                 "wikipedia/commons/f/fa/",
                 "Eilenburg_Blumenuhr2.jpg"),
          tags$small("Users own work, Photographed by Joebo7 3rd May 2009",
                  a(href="http://commons.wikimedia.org/wiki/File%3AEilenburg_Blumenuhr2.jpg")))
```

<!--html_preserve--><img class="img-polaroid" src="http://upload.wikimedia.org/wikipedia/commons/f/fa/Eilenburg_Blumenuhr2.jpg">
<small>
Users own work, Photographed by Joebo7 3rd May 2009
<a href="http://commons.wikimedia.org/wiki/File%3AEilenburg_Blumenuhr2.jpg"></a>
</small>
</img><!--/html_preserve-->

