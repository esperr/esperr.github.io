---
layout: post
title:  "Plotting Ideology vs Engagement"
date:   2019-08-28
categories: data_visualization programming congress
---

Introducing a new visualization in Members by Interest -- scatter plots that show the relationship between a member’s engagement with a given topic (as measured by [adjusted score](https://esperr.github.io/members-by-interest/about.html#howtoadjust)) and their ideology (as measured by Dimension 1 [DW-NOMINATE](https://voteview.com/about) scores).

As noted before, adjusted scores measure a member's interest in a given topic as reflected by those measures about that topic (as cataloged by the folks at LC) that they sponsor and cosponsor. These scores are the same ones that drive the existing visualizations where members are ranked by the intensity of their legislative interests. What’s new with visualization is the incorporation of DW-NOMINATE scores.

The Dynamic Weighted NOMINAl Three-step Estimation metric was pioneered by Keith T. Poole and Howard Rosenthal at Carnegie-Mellon University. The system they developed plots members along axes of “left” and “right” (the Dimension 1 used in this visualization) and other pressing issues of the day (Dimension 2). This plotting is based on comparing roll call votes to one another and is further described in Poole's [Spatial Models of Parliamentary Voting](https://www.cambridge.org/catalogue/catalogue.asp?isbn=9780521617475).

As with the ranked view, users can examine data for both [Policy Areas](https://www.congress.gov/help/field-values/policy-area) and [Legislative Subject Terms](https://www.congress.gov/help/field-values/legislative-subject-terms). Unlike the ranked view, users will be limited to viewing results for an individual congress (DW-NOMINATE scores for the same member may vary by congress).

Sometimes there are strong correlations between ideology and subject engagement, as with the Policy "[Civil Rights and Liberties, Minority Issues](https://esperr.github.io/members-by-interest/nomscatter.html?congress=116&chamber=house&subjecttype=policy&subject=Civil Rights and Liberties, Minority Issues)":  

<img src="/assets/civilrightsscatter.PNG" width="700">

...or the Legislative Subject "[Abortion](https://esperr.github.io/members-by-interest/nomscatter.html?congress=116&chamber=house&subjecttype=subject&subject=Abortion)":

<img src="/assets/abortionscatter.PNG" width="700">

In other cases there seems to be little obvious relationship between engagement and ideology, as with "[Native Americans](https://esperr.github.io/members-by-interest/nomscatter.html?congress=116&chamber=house&subjecttype=policy&subject=Native Americans)":

<img src="/assets/nativeamericanscatter.PNG" width="700">

If you hover over a point, you see the member in question, as well as how many measures she has sponsored and cosponsored about that topic.

As always, contact me if you have any questions or suggestions.
