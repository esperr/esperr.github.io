---
layout: post
title:  "The Littlest Webservice"
date:   2017-05-03
categories: programming
---
As (hopefully) demonstrated by [Visualizing PubMed](/visualizingpubmed), there is almost no end to the cool things you can do using the [E-Utilities](https://dataguide.nlm.nih.gov/) API to PubMed (and other NCBI databases). However, there are some limitations that one needs to keep in mind when developing interactive tools. Chief among these is the admonition that one should make [no more than three requests per second to the API](https://www.ncbi.nlm.nih.gov/books/NBK25497/#_chapter2_Usage_Guidelines_and_Requiremen_).

This becomes an issue in use cases such as [PubMed by Year](https://esperr.github.io/pubmed-by-year/), where we would seem to need lots of individual searches. For example, if we need counts for "myexamplesearch" from 1945 to the present in order to compare them to baseline, the most direct solution would be to send multiple requests:

 `https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esearch.fcgi?db=pubmed&term=myexamplesearch+AND+1945[DP]`

 `https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esearch.fcgi?db=pubmed&term=myexamplesearch+AND+1946[DP]`

 `https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esearch.fcgi?db=pubmed&term=myexamplesearch+AND+1947[DP]`

 ...etc

That works, but it also comes to 72 requests per graph. If we're adhering to the rules and waiting 1/3 of a second between each request, it's going to take us 24 seconds to get our counts. What can we do instead?

Close observers will note that there is a "Download CSV" link underneath the "Results by Year" widget that shows up for any PubMed search with 500 hits or more. Sadly, there is no way to directly get this link using the API, but we could just try to scrape it off the PubMed results page and then urlfetch the CSV.

Due to the way that PubMed pages are served, there's not an easy way to get a static URL off the bat, but we can scrape the value for "blobid". Once we have that, we can combine it with our original search like so:

~~~~
csvstem = "https://www.ncbi.nlm.nih.gov/pubmed?p$l=Email&Mode=download&dlid=timeline&filename=timeline.csv"
try:
    validate_certificate = 'true'
    csvurl = csvstem + "&term=" + searchstr + "&bbid=" + blobId + "&p$debugoutput=off"
    result = urlfetch.fetch(csvurl)
~~~~
(see the full code [here](https://github.com/esperr/med-by-year/blob/master/main.py))    

With the resulting CSV, we now have counts for all possible years (currently back to 1809 for the smattering of older PubMed Central stuff) in two requests instead of bunches.
