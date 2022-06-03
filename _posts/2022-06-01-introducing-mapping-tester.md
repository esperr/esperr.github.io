---
layout: post
title:  "Introducing Mapping Tester!"
date:   2022-06-03
categories: PubMed
---
The newest version of [PubMed](https://pubmed.ncbi.nlm.nih.gov/) has brought a lot of changes, including the '[Best Match](https://support.nlm.nih.gov/knowledgebase/article/KA-03719/en-us)' results sort. Another, less obvious change, is an update to how [Automatic Term Mapping](https://www.youtube.com/watch?v=MQ-ttxlkN2U) (ATM) works in the new version. Sometimes the 'new' mapping is exactly the same as the 'old', but sometimes it's different enough to lead to noticeable changes in a search strategy that was developed before the switchover. Now thanks to an API from we can test and see for sure!

The production version of the [eutils](https://www.ncbi.nlm.nih.gov/books/NBK25501/) API points to 'old' PubMed, including the older version of ATM, but there is now [a test server](https://ncbiinsights.ncbi.nlm.nih.gov/2022/03/24/test-server-pubmed-api/) that uses the new ATM mapping (and also lets us get "Best Match' sorting programmatically). Since we have both the 'old' version of the API as well as the new one, that makes it possible to run the same search against both, and see if there are any differences. A little bit of JavaScript, and et voilà!
[https://esperr.github.io/mapping-tester](https://esperr.github.io/mapping-tester)

There are many cases where the mapping is exactly the same, such as with "viral infection":

<img width="85%" src="/assets/viral_infection_mapping.png" alt="Old and new mapping for 'viral infection'">
<br><br>
In other cases, as with "influenza", the new mapping algorithm includes a plural form or synonym that makes a significant difference (in this case, 21% greater retrieval):

<img width="85%" src="/assets/influenza_mapping.png" alt="Old and new mapping for 'Influenza'">
<br><br>
In some cases, the differences are so radical that it seems that they must have been intentionally hand-tweaked. In this case, there is a *lot* (7.5x more) captured by the new mapping for "diabetes medication" that was missing before:

<img width="85%" src="/assets/diabetes_medication_mapping.png" alt="Old and new mapping for diabetes medication'">
<br><br>
So does this mark a conscious effort to increase retrieval for a beginner-level search for medications? It certainly seems deliberate. Indeed, I imagine some sort of user testing by the friendly folks on the PubMed UX team was involved. This is the sort of change that is very dramatic, but shouldn't affect the more complex, fielded searches done by a medical librarian (as they are less subject to modification by ATM in the first place). But as advanced PubMed users know, ATM can be...persistent, so it may be worth checking a recurring search that you developed before the handover to 'new' PubMed.
