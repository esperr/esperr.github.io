---
layout: post
title:  "Things may be slower than usual..."
date:   2019-01-07
categories: programming
---

As noted in an [earlier post]({{ site.baseurl }}{% post_url 2017-05-03-the-littlest-webservice %})
, NCBI wants one to restrict calls to [E-Utilities](https://dataguide.nlm.nih.gov/) to no more than [three per second](https://www.ncbi.nlm.nih.gov/books/NBK25497/#_chapter2_Usage_Guidelines_and_Requiremen_).

If (like me) you are a developer who uses this interface on a regular basis, you may have noticed that NCBI has gotten a *lot* more aggressive about enforcing this limit. To wit, you will now start regularly getting an error if you exceed it from a given IP address. One way around this is to request an [API key](https://ncbiinsights.ncbi.nlm.nih.gov/2017/11/02/new-api-keys-for-the-e-utilities/) to sign requests with. This will get you 10 requests per second instead.

 However this API key then applies to all applications (from all IP addresses) using it. It would still be possible for two or three simultaneous users with the same API key to exceed this limit and so lock access for everybody else. I am therefore modifying [Search Workbench](https://searchworkbench.info/) and the other pieces of [Visualizing PubMed](https://esperr.github.io/visualizingpubmed/) to only. call. every. 400. milliseconds (plus or minus a bit). You many notice a lag with some applications that make a lot of calls (such as [Mapping MEDLINE](https://esperr.github.io/mapping-medline/) ).

 Do let me know if you encounter any problems with these applications...
