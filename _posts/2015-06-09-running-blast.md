---
layout: page
category: usage
title: "Running BLAST+"
order: 5
---
The BLAST server image already has the BLAST+ applications ([publication](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2803857/), [quick start](https://www.ncbi.nlm.nih.gov/books/NBK279680/), [cookbook](https://www.ncbi.nlm.nih.gov/books/NBK279696/)) installed and will
retrieve the databases listed [here]({{site.baseurl}}{% post_url 2015-06-09-available-blastdbs %}) on demand (i.e.: when the first BLAST search of that BLAST database occurs). 
Users familiar with command line interfaces can run the BLAST+ applications directly on their 
instance by [logging on via ssh]({{site.baseurl}}{% post_url 2015-06-09-logging-in %}) (requires [setting up remote access]({{site.baseurl}}{% post_url 2015-06-09-setting-up-remote-access %}))
and issuing commands at the terminal prompt.
