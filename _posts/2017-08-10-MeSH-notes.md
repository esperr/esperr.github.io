---
layout: post
title:  "MeSH Notes"
date:   2017-08-10
categories: MEDLINE
---
Just (virtually) attended [Advanced PubMed: MeSH](https://nnlm.gov/class/advanced-pubmed-mesh/7583) from [NNLM](https://nnlm.gov/). Very cool! I was playing around in [PubVenn](https://pubvenn.appspot.com/) with some of the examples we covered, and I found some (potentially) interesting things.

["Depression"[mesh]](https://meshb.nlm.nih.gov/record/ui?ui=D003863) describes a related-but-separate concept from ["Depressive Disorder"[mesh]](https://meshb.nlm.nih.gov/record/ui?ui=D003866), and they live on different branches of the [MeSH tree](https://meshb.nlm.nih.gov/treeView). Functionally however, Depressive Disorder ends up being a narrower heading of Depression:

<img src="/assets/depressionvsdepressive.png" width="500">

 (<a href='https://pubvenn.appspot.com/?depression%5Bmesh%5D%20OR%20%22depressive%20disorder%22%5Bmesh%5D'>see more at PubVenn</a>)

<p style="font-size: 2em; text-align: center;">&#9830;</p>

How much overlap would you expect between ["Poisoning"](https://meshb.nlm.nih.gov/record/ui?ui=D011041) the MeSH heading and ["/poisoning"](https://www.ncbi.nlm.nih.gov/mesh/81000506) the subheading? It makes sense that they would be at least a *little* different, given the admonishment in the annotation to "prefer /pois with Category D & J terms". Would it surprise you to find that they overlap by a little less than a third?

<img src="/assets/poisoningvspoisoning.png" height="500px">

(<a href="https://pubvenn.appspot.com/?poisoning[mesh]%20OR%20poisoning[subheading]">see more at PubVenn
</a>)

<p style="font-size: 2em; text-align: center;">&#9830;</p>

Lastly, I was reminded that subheadings, just like other descriptors, can be broad or narrow (and that the broad ones are exploded by default). This diagram isn't so much revelatory as it is just pretty...

<img src="/assets/aeexplode.png" height="500px">

(<a href='https://pubvenn.appspot.com/?%22adverse%20effects%22%20%5BSubheading%5D%20AND%20%22poisoning%22%20%5BSubheading%5D%20AND%20%22toxicity%22%20%5BSubheading%5D'>See more at PubVenn</a>)
