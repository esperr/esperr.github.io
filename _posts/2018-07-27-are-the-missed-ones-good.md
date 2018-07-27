---
layout: post
title:  "Are Narrow NOT Broad citations any good?"
date:   2018-07-27
categories: PubMed
---

One critique I received on [my presentation](https://osf.io/ytbc6/) about what gets missed when only using the "Broad" version of the [PubMed clinical queries](https://www.ncbi.nlm.nih.gov/pubmed/clinical) was that maybe the citations missed were not "true positives". That is, they might have characteristics in common that make them both invisible to the Broad query and also somehow less fit for purpose than their Narrow AND Broad fellows.

One relatively straightforward way to test this hypothesis is by using the work of the [HIRU group](https://hiru.mcmaster.ca/hiru/Default.aspx) at McMaster who originally developed the clinical  queries. They curate a database called [McMaster Plus](https://hiru.mcmaster.ca/hiru/hiru_mcmaster_plus_projects.aspx). Articles in this database are carefully evaluated as to whether they meet the relevant [inclusion criteria](https://hiru.mcmaster.ca/hiru/InclusionCriteria.html), so it can be presumed that they are "good". Indeed, inclusion in this database was used as the test criteria for their [2012 revalidation study](https://academic.oup.com/jamia/article/20/2/363/898052) of the clinical queries. Therefore, one way to see whether or not Narrow NOT Broad citations are good ones is to see whether they show up in McMaster Plus.

Using some common clinical terms (such as "heart disease", "breast cancer", etc.) and the "Prognosis" category,  I selected and downloaded a set of 1,021 Original Study citations from the McMaster Plus database via the [Accessss interface](https://www.accessss.org/). PMIDs were extracted from each citation, and these were searched against PubMed using the [NCBI eutils](https://www.ncbi.nlm.nih.gov/books/NBK25500/), testing whether each one showed up under Prognosis/Broad, Prognosis/Narrow or Prognosis/Narrow NOT Prognosis/Broad.

The results were clear -- many of these presumptively good citations exhibited the same behavior as noted in my original report. That is, they can be found using the Prognosis/Narrow clinical query but *not* when searching with Prognosis/Broad. Indeed, a little over 15% of the citations tested were missed when using Prognosis/Broad alone (Narrow OR Broad: 875, Narrow NOT Broad: 139). Whatever ways these Narrow NOT Broad citations may differ from those found using Broad alone, they *cannot* be assumed to be substandard.
