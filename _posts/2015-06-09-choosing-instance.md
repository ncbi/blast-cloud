---
layout: page
category: doc
title: "Choosing an instance"
order: 8
---

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

