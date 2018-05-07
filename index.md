---
layout: page
title: "NCBI BLAST Cloud Documentation"
---

### Background

Basic Local Alignment Search Tool (BLAST) is a popular sequence similarity
search tool. The National Center for Biotechnology Information (NCBI) maintains
a public BLAST server at
[blast.ncbi.nlm.nih.gov](https://blast.ncbi.nlm.nih.gov). The NCBI BLAST server
is intended mainly for interactive use, with the expectation that users will
perform a moderate number of searches (i.e., 10-20) per day. Some users have
many more searches to perform than can be accommodated at the NCBI site. For
such batch users, the NCBI offers the stand-alone BLAST+ package that can be
run on local hardware. Running the stand-alone package requires that the user
have access to sufficient compute resources (e.g., a local cluster) as well as
some degree of familiarity with IT issues and command-line applications.
Additionally, some users do not need to perform a large number of searches on a
regular basis, but may need to do so occasionally. A cloud provider may offer
an acceptable solution for these batch users.

### Running BLAST on the Amazon cloud

The NCBI provides a BLAST server image at Amazon Web Services
(AWS).  The BLAST server image includes a web application that provides
a simplified BLAST search web page and supports the [NCBI-BLAST Common URL API]({{ site.baseurl }}{% post_url 2015-06-09-api %}), 
the BLAST+ applications, 
and a "FUSE" client that can cache databases from the NCBI (during the first search).
The instance runs an HTTP server for the remote BLAST searches. The FUSE client can download
a limited set of databases (see [the FUSE client]({{ site.baseurl }}{% post_url 2015-06-09-fuse %})). 
NCBI does not not charge for use of the software, but any instances will
incur the cloud provider's charges.

* The AWS Amazon Machine Image (AMI) can be run directly via the [AWS
Marketplace](https://aws.amazon.com/marketplace/pp/B00N44P7L6).

The BLAST server image supports three different search methods:

1. Users can ssh into the instance and [run stand-alone BLAST+ at the
command-line]({{ site.baseurl }}{% post_url 2015-06-09-running-blast %}). 
1. The instance has a [simple webpage for search submission]({{ site.baseurl }}{% post_url 2015-06-09-running-web-blast %}). 
1. The instance supports the [NCBI-BLAST Common URL API interface]({{ site.baseurl }}{% post_url 2015-06-09-api %}). 

The latter two methods are remote searches that return a "Request ID" and **require** [authentication]({{ site.baseurl }}{% post_url 2015-06-09-authentication %}).
