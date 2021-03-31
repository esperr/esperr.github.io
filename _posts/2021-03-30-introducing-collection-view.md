---
layout: post
title:  "Introducing Collection View!"
date:   2021-03-30
categories: data_visualization
---
A few days back, I had the distinct pleasure of debuting my newest project, [Collection View](https://esperr.github.io/collection-view/), at my talk "Looking Beyond the List: Enhancing Search with Interactive Visualizations" at [Code4Lib 2021](https://2021.code4lib.org/). You can find the slides for that talk at [osf](https://osf.io/acm3q/) and the recording on [YouTube](https://www.youtube.com/watch?v=QC_R2IkYzao).

One issue with large bibliographic databases is that many searches return hundreds if not thousands of results. Ideally, much of what a user is looking for will be concentrated in the first few dozen results, as those are likely the only results they will ever look at. Otherwise that user should revise their search, but how do they know if those changes are doing any good?

Here is where visualizations can help! [Collection View](https://esperr.github.io/collection-view/) is designed to translate your [Library of Congress](https://www.loc.gov/) search into simple visualizations that give you an instant *summary* of the kinds of materials that are being returned as well as showing how their proportions compare to those of the collection as a whole.

<img width="75%" src="/assets/viruses.png" alt="Formats for 'viruses'">
<img width="75%" src="/assets/suez-centuries.png" alt="Century proportions for the phrase 'Suez Canal'">

Much like [Search Workbench](https://searchworkbench.info/), it also uses Venn diagrams to illustrate how parts of complex search relate to one another. For example, if someone were to search using Boolean logic for "Art Nouveau AND furniture":

<img width="75%" src="/assets/art-nouveau-and-furniture.png" alt="Venn diagram showing sets for 'Art Nouveau AND furniture'">

Crucially, it also (as [Search Workbench](https://searchworkbench.info/) does) allows you to visually *compare* multiple searches to one another, facilitating the process of refining a complex search strategy. For example, the results returned by the search "container shipping" are not at all the same as those found with "shipping container":

<img width="75%" src="/assets/shipping-container-vs-container-shipping.png" alt="Venn diagram comparing sets for 'shipping container' and 'container shipping'"><a href="mailto:ed_sperr@hotmail.com">

[Collection View](https://esperr.github.io/collection-view/) uses the [Library of Congress API](https://libraryofcongress.github.io/data-exploration/) maintained by [LC Labs](https://labs.loc.gov), so any search that runs against their database can be visualized! As always, <a href="mailto:ed_sperr@hotmail.com">let me know</a> if you have any questions or comments.
