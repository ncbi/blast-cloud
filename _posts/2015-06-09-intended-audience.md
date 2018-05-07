---
layout: page
category: doc
title: "Intended Audience"
order: 0
---

The NCBI BLAST AMI will be useful to end users with lots of BLAST searches to run and/or those who have proprietary sequence data that want to run with BLAST. Having familiarity with cloud services is helpful, but not mandatory, as the AWS Marketplace provides a 1-Click-Launch option and documentation on how to start/stop your instances. If you run into any difficulty, please feel free to email us at blast-help@ncbi.nlm.nih.gov so we can help you!

The 1-Click-Launch options is configured by default to start a large enough instance to run searches against the nr and nt BLAST databases and store the results in the instance's local disk.

FIXME: add section with table?

For those users with proprietary sequence data, you can convert that sequence data into BLAST databases and upload the resulting BLAST databases to a running instance (see last paragraph here). 

## Use cases

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
