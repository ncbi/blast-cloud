---
layout: page
category: conf
title: "How to choose an instance?"
order: 0
---

### BLAST performance

BLAST performs best when the BLAST database's sequence data can fit into RAM (see section below), so BLAST
searches will not run efficiently on smaller instances. Please see your cloud
provider for a [list of suitable instances](https://aws.amazon.com/ec2/instance-types/).

### BLAST database storage

The server image is designed to use a local "scratch" disk to speed up the
BLAST database. For AWS, you need to ensure that your instance has 'instance
storage' and that it is attached.

**NOTE**: If you intend to stop and re-start an instance, please choose an AWS
instance type that has EBS as its storage. If SSDs are used, their contents will be 
lost after the instance is rebooted or restarted.

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
