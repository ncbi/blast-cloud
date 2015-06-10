---
layout: page
title: "NCBI BLAST AMI Documentation"
---

Basic Local Alignment Search Tool (BLAST) is a popular sequence similarity
search tool. The National Center for Biotechnology Information (NCBI) maintains
a public BLAST server at
[blast.ncbi.nlm.nih.gov](http://blast.ncbi.nlm.nih.gov). The NCBI BLAST server
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

The NCBI is experimenting with a BLAST+ installation at Amazon Web Services
(AWS). The NCBI is providing an Amazon Machine Image (AMI) which can be run
directly and via the [AWS
Marketplace](https://aws.amazon.com/marketplace/pp/B00N44P7L6). The BLAST AMI
includes the BLAST+ applications, a "FUSE" client that can cache databases from
the NCBI (during the first search), a PERL script that mimics a subset of the
NCBI URL API, and a simplified BLAST search webpage. The instance runs an http
daemon for the remote BLAST searches. The FUSE client can download a limited
set of databases (see [the FUSE client]({% post_url 2015-06-09-fuse %})). 

The BLAST AMI supports three different search methods:

1. Users can ssh into the instance and run stand-alone BLAST at the command-line. 
2. The instance has a simple webpage for search submission. 
3. The instance supports a **_subset_** of the NCBI-BLAST URL API interface
(see [API]({% post_url 2015-06-09-api %})). 

The latter two methods are remote searches that return a "Request ID".

The remote search methods allow one user in a group to register at AWS,
configure the instance, and handle payment for the EC2 instances (NCBI does not
charge for use). Other
members of a group can then use the instance through the URL API or webpage
without their own AWS account. The URL API interface is ideal for users
familiar with the BLAST URL API at the NCBI. Currently, the BLAST AMI runs
searches on only one instance. Many simultaneous users, through the remote
interface, could overload a single instance. The NCBI is working on an approach
that distributes searches to multiple instances.
Information and links to the latest BLAST AMI are available at the [BLAST Searches at a Cloud Provider](http://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Web&PAGE_TYPE=BlastDocs&DOC_TYPE=CloudBlast) web page.

The NCBI welcomes feedback on this experiment at AWS. You may provide feedback using this [form](http://www.ncbi.nlm.nih.gov/sites/ehelp/feedback?Ncbi_App=blastAWS&Data=JiraApp:HD;).


