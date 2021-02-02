# GuitarMarkovChain

### Overview and Goals
The objective of this project is to Markov Chains to attempt to randomly generate a guitar song and output its TABs for a guitarist to play. This will be achieved by scraping thousands of  tablature/tabs (a type of song notation used by guitarists) from Ultimate Guitar's website to gather data in order to develop a Markov Model. This model can then be used to generate a guitar tablature based off of the statistical data scraped from all the songs from Ultimate Guitar. We'll be able to see if statistics can generate a good sounding song!

### Current Status
Currently, the tab scraper program is almost complete and can successfully scrape and store about a thousand songs' data at a time. The song generator can create a graph based off of the notes scraped and create a Markov Model. It is able to generate a song and output it into a text file in a human readable format. However, the songs do not sound great currently and thus the Markov Model requires some adjusting and tuning.

### How To Use
(Work in progress to make user-friendly)

### Future Plans
* Create some type of algorithm to group together similar notes in order to improve the Markov Model by decreasing the number of nodes in the graph and increasing the number of outgoing edges from each node
* Make a slightly more user-friendly interface
* Use this as an opportunity to learn about SQL in order to make the scraper store songs using SQL rather than locally in pickle files
* Figure out how to use some api to play the songs from the program rather than having to copy paste the outputted tab into a tabs player
* Add support for tabs that use a capo (should be an easy one)

#### Known Issues / Challenges

* Currently, the scraper has to "screen scrape", which means it manually parses the html on the page. This is because I had trouble finding where the data is actually stored and could not find any api to access it from. As a result, due to inconsistencies in formatting on some of the songs, not all songs are sucessfully scraped, with a roughly 75% success rate.

* The Markov Model is currently designed so that each note in a song is a node in the graph with directed edges to each next note found by scraping the songs. However, because of this approach, very similar notes are still considered to be unique nodes leading to too many nodes in the graph with too few outgoing edges.
For example, all of the notes in the following tab are very similar but still counted as different notes. Some typing of clustering algorithm may improve this resulting in better quality songs being generated.
```
-----------------
--2---2---2---2--
-----------------
----------0---0--
------0-------0--
-----------------
```





