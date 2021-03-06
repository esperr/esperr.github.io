---
layout: page
title: Visualizing PubMed
permalink: /visualizingpubmed/
---

# Rationale

[PubMed](https://www.ncbi.nlm.nih.gov/pubmed/) is an invaluable resource, enabling searching of a large portion of the biomedical literature and serving as perhaps the most popular entry point to [MEDLINE](https://www.nlm.nih.gov/pubs/factsheets/medline.html). As an interface however, it is primarily geared towards presenting results in the form of a long, paginated list. This works well for examining individual citations, but is a poor fit for getting a larger sense of how one search compares to another (or how the results of a particular search compare to the database as a whole). For this purpose, it would be better to see searches in aggregate. Even better would be to display and compare searches using a variety of criteria.

# Methods

Using the [NCBI API (E-utilities)](https://www.ncbi.nlm.nih.gov/books/NBK25497/), I have developed a series of tools to visualize PubMed searches. Querying of the API and parsing of the results is done in the browser via [JavaScript](https://www.javascript.com/) and the [jQuery library](https://jquery.com/). Visualization of results is also done in the browser (for the most part with [Google Charts](https://developers.google.com/chart/) and with the [venn.js](https://github.com/benfred/venn.js/) overlay of [d3.js](https://d3js.org/) for Venn diagrams).

# Results

### [PubTrees](https://esperr.github.io/pub-trees/)

<img src="/assets/PubMed.PNG" style="float:right;width:300px;padding-left:1em;">

PubTrees ([https://esperr.github.io/pub-trees/](https://esperr.github.io/pub-trees/)) enables you to explore the concepts in the documents returned by your PubMed search by using the [Word Tree](http://hint.fm/papers/wordtree_final2.pdf) technique first developed by Martin Wattenberg and Fernanda B. Viégas. Much like word clouds, Word Trees provide information about the frequency of terms. Crucially, they also reveal the *context* in which those terms are used by showing the frequency of word sequences.

<br style="clear:both;" />

### [Search Workbench](https://searchworkbench.info/)

Search Workbench ([https://searchworkbench.info/](https://searchworkbench.info/)) is a workspace for visualizing individual searches as well as making visual comparisons between different results sets. This tool enables you to easily see how changes in your search strategy affect your results in real time. The goal is to streamline the process of refining a search so that you can spend less time dialing-in your search strategy and more time examining your results.

<br style="clear:both;" />

### [PubMed by Year](https://esperr.github.io/pubmed-by-year/)

<img src="/assets/zikadengueyear.png" style="float:right;width:300px;padding-left:1em;">

PubMed by Year ([https://esperr.github.io/pubmed-by-year/](https://esperr.github.io/pubmed-by-year/)) shows your search on a line chart, comparing the results for each year to the database as whole. We use proportions instead of raw numbers, as the the astonishing increase of the biomedical literature over time makes a bare count less illustrative of changes for any given search. Helpfully, you can add additional searches so you can directly compare how different topics have been treated over time.

Note: As PubMed by Year uses the "Results by Year" CSV file generated by PubMed, it does not work for searches that return fewer than 500 total results (because that file doesn't get generated for smaller result sets).

<br style="clear:both;" />

### [PubVenn](https://pubvenn.appspot.com/)

<img src="/assets/diabvenn.png" style="float:right;width:300px;padding-left:1em;">

Venn diagrams have been used by librarians for ages to help users visualize how complex searches work. PubVenn ([https://pubvenn.appspot.com/](https://pubvenn.appspot.com/)) takes a complex PubMed search and divides it into its constituent parts. It then searches those disparate parts and shows the piles of citations they return using a proportionally-sized venn diagram.

Searches can be simple or complex, though plotting intersections onto a two-dimensional plane can be somewhat inexact for any diagram involving more than two sets.
<br style="clear:both;" />

### [MeSH Category Graph](https://esperr.github.io/mesh-cat-graph/)

<img src="/assets/myoinfarctcat.png" style="float:right;width:300px;padding-left:1em;">

MeSH Category Graph ([https://esperr.github.io/mesh-cat-graph/](https://esperr.github.io/mesh-cat-graph/)) Graphs a search against the the [16 top-level categories](https://www.nlm.nih.gov/bsd/disted/meshtutorial/meshtreestructures/) in the [MeSH hierarchy](https://meshb.nlm.nih.gov/search). For each search you'll see two graphs — one showing percentages compared to those for all of MEDLINE and another showing relative proportion.

Once you have completed at least two searches, you can compare the proportions of one search against another.

<br style="clear:both;" />

### [MeSH Subheading Graph](https://esperr.github.io/mesh-subhead-graph/)

<img src="/assets/myoinfarctsub.png" style="float:right;width:300px;padding-left:1em;">


MeSH Subheading Graph ([https://esperr.github.io/mesh-subhead-graph/](https://esperr.github.io/mesh-subhead-graph/)) Graphs a search against the 23 top-level subheadings ("analysis", "physiology", etc.) in the [MeSH qualifier hierarchy](https://www.nlm.nih.gov/mesh/subhierarchy.html). As above, results are displayed in two ways, and any two searches can be compared with one another.

<br style="clear:both;" />

### [Mapping MEDLINE](https://esperr.github.io/mapping-medline/)

<img src="/assets/stomachcancer-asia.png" style="float:right;width:300px;padding-left:1em;">

 MeSH headings include not only topic areas but geographic regions — around 15% of all indexed records are tagged with the name of a continent, country or city. Mapping MEDLINE ([https://esperr.github.io/mapping-medline/](https://esperr.github.io/mapping-medline/)) searches your results against these geographical headings. Of course some articles might mention a country name in a title or abstract without a corresponding index term, so Mapping MEDLINE searches those fields by country name as well. Results are displayed as a choropleth map (shaded by proportion) in order to better reflect regional variation.

 <br style="clear:both;" />


You can find the source code for each of these applications at
{% include icon-github.html %} [github/esperr](https://github.com/esperr?tab=repositories)
