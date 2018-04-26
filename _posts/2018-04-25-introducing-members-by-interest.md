---
layout: post
title:  "Introducing Members by Interest"
date:   2018-04-18
categories: data_visualization programming
---

[Members by Interest](https://esperr.github.io/members-by-interest/) is another entry for the [Congressional Data Competition](https://www.challenge.gov/challenge/congressional-data-competition/).

When you examine the XML files at the [GPO's Bulk Data Bill Status page](https://www.gpo.gov/fdsys/bulkdata/BILLSTATUS), you find that there is a wealth of data about each item, all lovingly detailed in [the accompanying manual](https://github.com/usgpo/bill-status/blob/master/BILLSTATUS-XML_User_User-Guide.md#2.-XML-Descriptions). For this project though, I wanted to concentrate on two pieces of information: who were the sponsors and cospsonsors of a given bill or resolution, and what that item was about.

The hope is to to give a sense of whether individual members of congress differ in their interests (as reflected in the bills that they sponsor or cosponsor). To quote the [about page](https://esperr.github.io/members-by-interest/about.html):

> One member may be very interested in farming, while another concerns herself primarily with foreign
> affairs. It is possible to guess at some of these interests by looking at geographical region or committee
> assignments, but a more direct route is to examine the types of bills that an individual member sponsors
> and cosponsors. This is useful information not only to observers of congress, but also for citizens who are
> especially concerned with a given issue.

The "aboutness" of an item is determined by looking at the indexing that is helpfully [provided by the Congressional Research Service](https://www.congress.gov/help/faq/find-bills-by-subject). Notably, every bill and resolution is assigned a single [Policy Area](https://www.congress.gov/help/field-values/policy-area) term that attempts to categorize what it is about in a broad sense. In addition, it is described using several different [Legislative Subject Terms](https://www.congress.gov/help/field-values/legislative-subject-terms) that give a more granular view.

The nuts and bolts are handled by a [Python script](https://github.com/esperr/members-by-interest/blob/master/buildsubjectlists.py) that pulls policy area/legislative subject terms from a batch of Bill status records and then totals up the sponsors and cosponsors associated with each one. That data is then rendered as JSON files that get fed to a front-end that either shows a ranked list for each area/subject, such as this one for "Libraries and archives" for the 133th through the 115th congresses (*Note: every sponsored bill counts for three cosponsored ones*)...

<img src="/assets/liblist.PNG" width="700">


...or generates a bar chart for the areas or subjects that are (proportionally speaking) most prominent in the bills sponsored or cosponsored by a particular member. For example, Rep. Clyburn (D-SC-6) has recently been an important member when it comes to items relating to the Caribbean:

<img src="/assets/clyburn.PNG" width="700">

...and Sen. Alexander (R-TN) has taken an interest in Animals:

<img src="/assets/alexander.PNG" width="700">
