---
layout: page
title: "NCBI BLAST Cloud Documentation"
---

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

The NCBI provides a BLAST+ server image at Amazon Web Services
(AWS), Google Compute Engine (GCE), and Microsoft Azure.  The BLAST server
image includes the BLAST+ applications, a "FUSE" client that can cache
databases from the NCBI (during the first search), a PERL script that mimics a
subset of the NCBI URL API, and a simplified BLAST search webpage. The instance
runs an http daemon for the remote BLAST searches. The FUSE client can download
a limited set of databases (see [the FUSE client]({{ site.baseurl }}{% post_url 2015-06-09-fuse %})). NCBI does not not charge for use of the software, but any instances will
incur the cloud provider's charges.

* The AWS Amazon Machine Image (AMI) can be run directly via the [AWS
Marketplace](https://aws.amazon.com/marketplace/pp/B00N44P7L6).
* The Google Compute Engine deployment process can be started from the [GCE Cloud
Launcher](https://console.developers.google.com/project/_/launcher/details/click-to-deploy-images/ncbiblast);
documentation can be found
[here](https://googlegenomics.readthedocs.org/en/latest/use_cases/run_familiar_tools/ncbiblast.html).
* The Microsoft Azure image can be started from the [Azure
Marketplace](https://azure.microsoft.com/en-us/marketplace/virtual-machines/all/?term=ncbi-blast).

The BLAST server image supports three different search methods:

1. Users can ssh into the instance and [run stand-alone BLAST+ at the
command-line]({{ site.baseurl }}{% post_url 2015-06-09-running-blast %}). 
1. The instance has a [simple webpage for search submission]({{ site.baseurl }}{% post_url 2015-06-09-running-web-blast %}). 
1. The instance supports the [NCBI-BLAST Common URL API interface]({{ site.baseurl }}{% post_url 2015-06-09-api %}). 

The latter two methods are remote searches that return a "Request ID".

The remote search methods allow one user in a group to register at a cloud
provider, configure the instance, and handle payment for the running
instance(s). Other members of a group can then use the instance through the URL
API or webpage without their own cloud provider account. The URL API interface
is ideal for users familiar with the BLAST URL API at the NCBI. Currently, the
BLAST server image runs searches on only one instance. Many simultaneous users,
through the remote interface, could overload a single instance. The NCBI is
working on an approach that distributes searches to multiple instances.
Information and links to the latest BLAST AMI are available at the [BLAST
Searches at a Cloud
Provider](https://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Web&PAGE_TYPE=BlastDocs&DOC_TYPE=CloudBlast)
web page.
