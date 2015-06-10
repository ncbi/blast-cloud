---
layout: page
category: doc
title: "Setting up BLAST"
order: 0
---
An account is required to run searches at AWS. An account may be obtained at http://aws.amazon.com (requires a credit card); please see the [EC2 documentation](http://docs.amazonwebservices.com/AWSEC2/latest/GettingStartedGuide/) [at AWS](http://aws.amazon.com/getting-started/) and their [pricing information](https://aws.amazon.com/ec2/pricing/). AWS also provides a [Command Line Interface](https://aws.amazon.com/cli/). 

The BLAST AMI can be started via the [AWS marketplace](https://aws.amazon.com/marketplace/pp/B00N44P7L6).
BLAST searches will not run efficiently on smaller instances. An instance with 32 GB of memory and a minimum of 32 GB SSD is required for reasonable performance.
In Marketplace, you can start with a smaller instance (`m3.2xlarge`) but your requirements may drive you to a large instance.

The nucleotide nt database contains about 56 billion bases (04/14/2014), but the sequence data is compressed 4-to-1. Hence, the sequences require about 14 GB. The protein nr database contains about 14 billion residues (04/14/2014), so the sequences require 14 GB. Experiments at the NCBI have shown that the `m3.2xlarge` instance ("General Purpose" with 30 GB of memory and SSD) as well as the `c3.4xlarge` ("Compute Optimized" with 30 GB of memory and SSD) instances are good choices for the BLAST AMI. The BLAST AMI will concatenate and construct a filesystem at first boot for the BLAST databases from all the attached ephemeral storage. Therefore, an `m3.2xlarge`, which may have up to two 80 GB ephemeral drives attached, may have 160 GB of BLAST database storage. The nr and nt databases will completely fill a 32 GB SSD (causing searches to fail), so a larger instance type than an `m3.large` should be selected if both protein and nucleotide databases will be searched. BLAST will not run on micro instances.

If you wish to allow remote searches, then you will need to enable HTTP access when you configure your instance. Please see [[Appendix 3]]. If you allow HTTP access, it is very important that you configure your security group properly. If the group is not restricted, anybody with knowledge of your public DNS may perform remote searches on your instance, see all the BLAST results for remote searches or delete the results. If possible, you should configure the security group of your instance to allow HTTP access only from a specific set of IP's (e.g. your lab's network). You should also only share the public DNS of your instance with people who have your permission to use it.

As a security precaution, the BLAST AMI blocks all ports but 22 and 80.
The BLAST results are kept on ephemeral storage. They will disappear when the instance is stopped or terminated. If you wish to keep them, then you should move them to permanent storage either at AWS or your institution.
