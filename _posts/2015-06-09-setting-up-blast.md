---
layout: page
category: doc
title: "Setting up BLAST"
order: 0
---
An account is required with one of the following cloud providers: Amazon Web Services (AWS), Google Compute Engine (GCE), or Microsoft Azure. As cloud providers rapidly change their product offerings, please consult their cloud documentation first.

NCBI does not charge for the use of our software but you will be billed by the
cloud provider. All costs associated with running the BLAST+ software in a
cloud provider are your own responsibility. Please ensure that you delete any
resources you are not using. The cloud providers all provide alerting services
to avoid unexpectedly large charges, NCBI suggests that you use these services.

For AWS, please see the [EC2 documentation](http://docs.amazonwebservices.com/AWSEC2/latest/GettingStartedGuide/) [at AWS](http://aws.amazon.com/getting-started/) and their [pricing information](https://aws.amazon.com/ec2/pricing/). AWS also provides a [Command Line Interface](https://aws.amazon.com/cli/). 

For GCE, complete documentation can be found at [Google](https://cloud.google.com/compute/docs/), the server image is distributed as a "click-to-deploy" option. Additional information can be found with [Google Genomics](http://googlegenomics.readthedocs.org/en/latest/use_cases/run_familiar_tools/ncbiblast.html).

The AWS server image can be started via the [AWS marketplace](https://aws.amazon.com/marketplace/pp/B00N44P7L6).

The GCE server image is a 'click-to-deploy' option and can be found at [Click-to-Deploy](https://console.developers.google.com/project/_/launcher/details/click-to-deploy-images/ncbiblast). 

The Azure server image can be found at the [Azure Marketplace](https://azure.microsoft.com/en-us/marketplace/partners/ncbi/ncbi-free-2-2-31/).

BLAST searches will not run efficiently on smaller instances. Minimally, an
instance with 32 GB of memory and a minimum of 32 GiB free space is required.
Please see your cloud provider for a list of suitable instances.

The server image is designed to use a local "scratch" disk to speed up the
BLAST database. For AWS, you need to ensure that your instance has 'instance
storage' and that it is attached. Google Compute Engine also requires attaching
a local, "scratch", SSD at boot. All Azure instances start with one local
"scratch" drive by default.

The nucleotide nt database contains about 56 billion bases (04/14/2014), but
the sequence data is compressed 4-to-1. Hence, the sequences require about 14
GB. The protein nr database contains about 14 billion residues (04/14/2014), so
the sequences require 14 GB. The nr and nt databases will completely fill a 32
GB SSD (causing searches to fail), so for AWS, a larger instance type than
`m3.large` should be selected if both protein and nucleotide databases will be
searched.

If you wish to allow remote searches, then you will need to enable HTTP access
when you configure your instance (please [Running Web BLAST]({{ site.baseurl }} {% post_url 2015-06-09-running-web-blast %}) and
[Common URL API]({{ site.baseurl }} {% post_url 2015-06-09-api %})). If you allow HTTP access, it is very important that you
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
