---
layout: page
category: usage
title: "Troubleshooting"
order: 7
---

If you have problems that are not addressed below, please do not hesitate to reach out to NCBI for help: blast-help@ncbi.nlm.nih.gov.

### The initial BLAST search takes too long

The BLAST databases are fetched from the NCBI (located in the east coast of North America), so if your instance is running in a region that is geographically far from NCBI, you will likely experience lengthy BLAST download times. Please see [how to choose a region]({{site.baseurl}}{% post_url 2015-06-09-data-center-location %}).

### BLAST takes too long

To run BLAST optimally, the BLAST database should fit in the host's main memory (i.e.: RAM). Please see [how to choose an instance]({{site.baseurl}}{% post_url 2015-06-09-choosing-instance %}).


  
