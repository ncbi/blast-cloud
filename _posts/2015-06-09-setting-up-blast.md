---
layout: page
category: doc
title: "Setting up BLAST"
order: 0
---
An account is required with Amazon Web
Services (AWS). As cloud providers rapidly change their product offerings, please consult their cloud documentation first.

NCBI does not charge for the use of our software but you will be billed by the
cloud provider. All costs associated with running the BLAST+ software in a
cloud provider are your own responsibility. Please ensure that you delete any
resources you are not using. The cloud providers all provide alerting services
to avoid unexpectedly large charges, NCBI suggests that you use these services.

For AWS, please see the [EC2 documentation](http://docs.amazonwebservices.com/AWSEC2/latest/GettingStartedGuide/) [at AWS](http://aws.amazon.com/getting-started/) and their [pricing information](https://aws.amazon.com/ec2/pricing/). AWS also provides a [Command Line Interface](https://aws.amazon.com/cli/). 

The AWS server image can be started via the [AWS marketplace](https://aws.amazon.com/marketplace/pp/B00N44P7L6).

### BLAST performance

BLAST performs best when the BLAST database's sequence data can fit into RAM, so BLAST
searches will not run efficiently on smaller instances. Please see your cloud
provider for a list of suitable instances.

### BLAST database storage

The server image is designed to use a local "scratch" disk to speed up the
BLAST database. For AWS, you need to ensure that your instance has 'instance
storage' and that it is attached.

The nucleotide `nt` database contains about 174 billion bases, but
the sequence data is compressed 4-to-1. Hence, the sequences require about 42
GB. The protein `nr` database contains about 54 billion residues, so
the sequences require 51 GB. The *total* size of the `nt` database as of this 
writing (03/15/2018) is 54 GB and the size of `nr` is 154 GB.
Please be sure to provision an instance with enough RAM and disk space for the BLAST
database(s) you will be using.

The instance downloads BLAST databases with a [FUSE client]({{ site.baseurl }}{% post_url 2015-06-09-fuse %}) 
from the NCBI during the first search of that database. This means that the
first BLAST search will be slow, but afterwards the database will be cached locally
and BLAST will run faster.

**NOTE**: Since the database is coming from the NCBI, downloads are faster if the
instance runs in a data center that is geographically close to NCBI.
For AWS, US-East (N. Virginia) is the closest data center, so for optimal performance, please consider
starting your instance in that data center.

### Setting up remote access

If you wish to allow remote searches, then you will need to enable HTTP access
when you configure your instance *and* provide [authentication]({{ site.baseurl }}{% post_url 2015-06-09-authentication %})
(please see [Running Web BLAST]({{ site.baseurl }}{% post_url 2015-06-09-running-web-blast %}) and
[Common URL API]({{ site.baseurl }}{% post_url 2015-06-09-api %})). If you allow HTTP access, it is very important that you
configure your security group/network firewall properly. If the group is not restricted, anyone
with knowledge of your public DNS may perform remote searches on your instance,
see all the BLAST results for remote searches or delete the results. If
possible, you should configure the security group/network firewall of your instance to
allow HTTP access only from a specific set of IP's (e.g. your lab's network). You should
also only share the public DNS of your instance with people who have your
permission to use it.

As a security precaution, the BLAST AMI blocks all ports but 22 and 80.
The BLAST results are kept on ephemeral storage. They will disappear when the
instance is stopped or terminated. If you wish to keep them, then you should
move them to permanent storage at your cloud provider or your institution.
