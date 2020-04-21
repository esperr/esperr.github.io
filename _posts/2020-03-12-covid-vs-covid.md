---
layout: post
title:  "Covid vs Covid"
date:   2020-03-12
categories: PubMed
---

Medical Librarians and other folks who search PubMed on a regular basis are likely familiar with the process of [Automated Term Mapping](https://www.youtube.com/watch?v=bhVVjGg5bIQ), where PubMed takes your search terms and "translates" them into different synonyms, variants and Medical Subject Headings. This process is often extremely helpful, but it does mean that small differences in the wording of your search can have big impacts on what it retrieves.

This can be seen clearly when comparing the two search terms "Covid19" and "Covid-19". ([view on PubVenn](https://pubvenn.appspot.com/?Covid19%20OR%20Covid-19#!))

<img src="/assets/covidvscovid.png" width="500">

Why the difference? In the first case, ATM in Legacy PubMed is rendering "Covid19" as
>"COVID-19"[Supplementary Concept] OR "COVID-19"[All Fields] OR "covid19"[All Fields]

...while in the second, "Covid-19" becomes (at least as of today)
>"COVID-19"[All Fields] OR "severe acute respiratory syndrome coronavirus 2"[Supplementary Concept] OR "severe acute respiratory syndrome coronavirus 2"[All Fields] OR "2019-nCoV"[All Fields] OR "SARS-CoV-2"[All Fields] OR "2019nCoV"[All Fields] OR (("Wuhan"[All Fields] AND ("coronavirus"[MeSH Terms] OR "coronavirus"[All Fields])) AND 2019/12[PDAT] : 2030[PDAT])

The "as of today" caveat is an important one. The National Library of Medicine has made clear that ATM mappings are subject to change and should not be regarded as immutable (or reproducible over time). With "Covid-19", it looks as if the mapping includes not only 'typical' translations, but  the NLM's [suggested interim search strategy](https://www.nlm.nih.gov/pubs/techbull/jf20/brief/jf20_mesh_novel_coronavirus.html) as well.

As always, if you're trying to put together a complicated search, consider using a tool like [Search Workbench](https://searchworkbench.info/) to validate it.
