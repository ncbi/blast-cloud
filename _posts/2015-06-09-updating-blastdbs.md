---
layout: page
category: blastdb
title: "Updating BLAST databases"
order: 1
---

There are two ways of updating the [BLAST databases]({{site.baseurl}}{% post_url 2015-06-09-available-blastdbs %}) 
that come installed by default in the BLAST AMI:


#### 1. Restart remote-fuser
[Login to the instance]({{site.baseurl}}{% post_url 2015-06-09-logging-in %}) and issue the following commands *when there are no BLAST searches running on your instance*:

    /sbin/remote-fuser-ctl.pl --stop
    /sbin/remote-fuser-ctl.pl --start

This will discard the already downloaded BLAST databases and switch to the latest available BLAST databases from NCBI.

#### 2. Restart the instance
[Stop]({{site.baseurl}}{% post_url 2015-06-09-stopping-instance %}) and [re-start]({{site.baseurl}}{% post_url 2015-06-09-starting-instance %}) the instance.
