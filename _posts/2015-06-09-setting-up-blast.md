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

For [AWS](http://aws.amazon.com/getting-started/), please see the [EC2
documentation](http://docs.amazonwebservices.com/AWSEC2/latest/GettingStartedGuide/)
and their pricing information for computational resources ([EC2](https://aws.amazon.com/ec2/pricing/)) and
storage ([EBS](https://aws.amazon.com/ebs/pricing/)). AWS
also provides a [Command Line Interface](https://aws.amazon.com/cli/). 

For GCE, complete documentation can be found at [Google](https://cloud.google.com/compute/docs/), the server image is distributed as a "click-to-deploy" option. Additional information can be found with [Google Genomics](http://googlegenomics.readthedocs.org/en/latest/use_cases/run_familiar_tools/ncbiblast.html).

The AWS server image can be started via the [AWS marketplace](https://aws.amazon.com/marketplace/pp/B00N44P7L6).

The GCE server image is a 'click-to-deploy' option and can be found at [Click-to-Deploy](https://console.developers.google.com/project/_/launcher/details/click-to-deploy-images/ncbiblast). 

The Azure server image can be found at the [Azure Marketplace](https://azure.microsoft.com/en-us/marketplace/partners/ncbi/ncbi-free-2-2-31/).

BLAST searches will not run efficiently on smaller instances. Minimally, as of
January 25, 2017, **an instance with 32 GB of memory and at least 200 GB of
disk space is required.** Please see your cloud provider for a list of suitable
instances.

The server image is designed to use a local "scratch" disk to speed up the
BLAST database. For AWS, you need to ensure that your instance has 'instance
storage' and that it is attached. Google Compute Engine also requires attaching
a local, "scratch", SSD at boot. All Azure instances start with one local
"scratch" drive by default.

The instance downloads a database with a [FUSE client]({{ site.baseurl }}{% post_url 2015-06-09-fuse %}) from the NCBI during the first search of that database. This means that the first search will be slow, but afterwards the database will be cached locally and run at normal BLAST speeds.  Since the database is coming from the NCBI, downloads are faster the closer the installation
is to the NCBI.  For AWS, US-East (N. Virginia) is the closest installation.

If you wish to allow remote searches, then you will need to enable HTTP access
when you configure your instance (please [Running Web BLAST]({{ site.baseurl }}{% post_url 2015-06-09-running-web-blast %}) and
[Common URL API]({{ site.baseurl }}{% post_url 2015-06-09-api %})). If you allow HTTP access, it is very important that you
configure your security group/network firewall properly. If the group is not restricted, anyone
with knowledge of your public DNS may perform remote searches on your instance,
see all the BLAST results for remote searches or delete the results. If
possible, you should configure the security group/network firewall of your instance to
allow HTTP access only from a specific set of IP addresses (e.g.: your lab's network). You should
also only share the public DNS of your instance with people who have your
permission to use it.

As a security precaution, the BLAST AMI blocks all ports but 22 and 80.
The BLAST results are kept on the instance's attached storage. 

At AWS, it is safe to reboot or stop and re-start the instance(s); the BLAST
databases and results will be preserved as long as the instance is not
terminated. However, you may incur in charges from the EBS volume attached to
any stopped instance(s). If you wish to keep the BLAST results after the
instance is terminated, then you should move them to permanent storage at your
cloud provider or your institution.
