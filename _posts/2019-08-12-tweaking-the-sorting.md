---
layout: post
title:  "Changing the formula for Members by Interest"
date:   2019-08-12
categories: data_visualization programming congress
---

I've made a small but important change to [Members by Interest](https://esperr.github.io/members-by-interest/). It currently uses an "adjusted score" when ranking a member's interest in a given topic as reflected by those measures about that topic (as cataloged by the folks at LC) that they sponsor and cosponsor. Sponsoring a bill or resolution counts for three points, being an "original" cosponsor counts for two points and joining as a cosponsor after a measure has been introduced counts for just one. This is intended to account for the fact that it is more difficult to sponsor a bill than to cosponsor another's, as well as the fact that an initial cosponsor may have had some input on a measure.  

After living with this for a bit, I think this formula undervalues the difference in effort between sponsoring a bill (or resolution) and cosponsoring someone else's measure. This is particularly true for broad Policy Areas such as "Health", where it seems to me that Reps. DeLauro and Burgess are both a little further down on this list than they should be:  

<img src="/assets/oldhealth.PNG" width="700">

Therefore, I am introducing a new formula: sponsoring a bill or resolution now earns a member one point, being an original cosponsor is worth .2 points and .1 point is awarded for cosponsoring after a measure is introduced. With sponsorship "worth" five times as much as original cosponsorship (and ten times as much as sponsorship after introduction), this scale seems to do a better job of ranking members according to the intensity of their engagement:

<img src="/assets/newhealth.PNG" width="700">

As before, the raw numbers of measures sponsored and cosponsored are listed below the member's name, so you're welcome to judge for yourself where they land on the list.

Importantly, this change in scoring pertains to the display of individual member's interests as well. For example, this graph of interests for Sen. Baldwin:

<img src="/assets/oldtammy.PNG" width="700">
<br />
...becomes under the new formula something very similar, but slightly different:

<img src="/assets/newtammy.PNG" width="700">

Again, you can double-check this sorting by clicking on the bars of the graph to see the measures in question.
