---
layout: page
category: usage
title: "Running BLAST+"
order: 2
---
The BLAST server image already has the [BLAST+ applications](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2803857/) installed and will
retrieve the databases listed [here]({{site.baseurl}}{% post_url 2015-06-09-available-blastdbs %}) on demand. 
Users familiar with command line interfaces can run the [BLAST+
applications](https://www.ncbi.nlm.nih.gov/books/NBK1763) directly on their 
instance by logging on via ssh (requires [setting up remote access]({{site.baseurl}}{% post_url 2015-06-09-setting-up-remote-access %}))
and issuing commands at the terminal prompt.

## Logging into the instance via ssh
The BLAST server image uses Ubuntu Linux, so you should use the user name `ubuntu`
rather than `root`, `centos`, `ec2-user`, or your own username for the ssh
connection. On Windows you can use [putty](https://www.putty.org/); in Linux and macOS you usually ssh is
available by default. 

