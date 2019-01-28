---
layout: post
title:  "(Re)Introducing Members by Interest"
date:   2019-01-28
categories: data_visualization programming congress
---

...Or how I learned to stop worrying and love having a database.

Last year I put together an application called [Members by Interest](https://esperr.github.io/members-by-interest/) to illustrate the particular interests of individual members of Congress by looking at the sorts of bills they sponsored and cosponsored.

At launch, the data driving the application was a series of (kinda large) static data files. This was
great from a performance standpoint, but the process of creating those files involved having a Python script parse each [Bill Status file](https://www.gpo.gov/fdsys/bulkdata/BILLSTATUS) from a given Congress before the files corresponding to that Congress could be written. When looking at the current Congress, this meant re-parsing hundreds (or thousands) of files every day that it was in session -- a process that was not only inelegant and resource-intensive, but one that made automating updates difficult.    

After some soul-searching (and confirming that the required database would fit within the [GCP Free Tier constraints](https://cloud.google.com/free/docs/gcp-free-tier), I wrote an application to download Status files and read 'em into a database. Once there, they can be queried, tallied up and fed to [an API](https://github.com/esperr/fetch-bill-statuses) for consumption.   

Of course re-writing the back-end meant some necessary changes to the front-end as well. This revision includes:

* A cleaned-up UI and Display. Ranked lists now show a clearer distinction between high and low scoring members and there is more emphasis on party ID.

* A revised method for computing the adjusted score that's used for both ranking members and showing individual member charts. It now takes into account the distinction between being a cosponsor and an original cosponsor -- the latter folks are the ones who are listed as cosponsors at introduction instead of having joined later, so there is a greater likelihood that they had input in constructing a given  measure.

Having a database as the back-end instead of static files also means that the range of questions that can be posed to the data is expanded as well! Watch this space...
