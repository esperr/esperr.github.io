---
layout: post
title:  "Updating News in Proportion"
date:   2020-11-10
categories: data_visualization programming newspapers
---

I've made a couple of updates to my project [News in Proportion](http://esperr.github.io/newsinproportion/). As before, this application renders a search of the items in [Chronicling America](https://chroniclingamerica.loc.gov/) into a choropleth map showing the relative proportion of results for each state. However, due to an increase of content in Chronicling America, it now covers a couple of states that it did not before: Maine, New Jersey and Wyoming. After closer examination, I also decided to remove Massachusetts from the counts -- at the moment, only one Massachusetts newspaper is included in Chronicling America (the Cronaca sovversiva), and the bulk of its text is in Italian.

Beyond that, I've removed the option to render raw counts (as opposed to proportions). Mapping raw counts either ends up swallowing up effects due to the differences in the total number of ChronAm pages per state, or it ends up being pretty much the same map as the proportional one. I've also made a couple of UI tweaks.

As always, <a href="mailto:ed_sperr@hotmail.com>let me know</a> if you have any comments, questions or brickbats...
