---
layout: page
category: blastdb
title: "Updating BLAST databases"
order: 1
---

If you run into any difficulty, please feel free to email us at blast-help@ncbi.nlm.nih.gov so we can help you!

### Updating the [available BLAST databases]({{site.baseurl}}{% post_url 2015-06-09-available-blastdbs %})

There are two ways of doing this:

#### Restart remote-fuser
[Login to the instance]({{site.baseurl}}{% post_url 2015-06-09-logging-in %}) and issue the following commands *when there are no BLAST searches running on your instance*:

    /sbin/remote-fuser-ctl.pl --stop
    /sbin/remote-fuser-ctl.pl --start

This will discard the already downloaded BLAST databases and switch to the latest available BLAST databases from NCBI.

#### Restart the instance
[Stop]({{site.baseurl}}{% post_url 2015-06-09-stopping-instance %}) and [re-start]({{site.baseurl}}{% post_url 2015-06-09-starting-instance %}) the instance.

### Installing other NCBI provided BLAST databases

Users may want to install other databases from the [NCBI FTP site](ftp://ftp.ncbi.nlm.nih.gov/blast/db) using the
`update_blastdb.pl` program. First, [log in to your running
instance via ssh]({{site.baseurl}}{% post_url 2015-06-09-logging-in %}) and run the
commands below :

    cd /blast/blastdb_custom
    update_blastdb.pl --decompress --passive <dbname>

### Installing your own BLAST databases

To achieve this, simply copy your BLAST database files onto the instance's `/blast/blastdb_custom` directory. E.g.:

    scp -i <PATH_TO_YOUR_SSH_KEY_FILE> <BLASTDB_FILES> ubuntu@<YOUR_INSTANCES_DNS>:/blast/blastdb_custom/


These (and any other) BLAST databases installed in the `/blast/blastdb_custom`
directory in the instance will be immediately available for searching via the
URL API, web interface, and BLAST+ command line applications on that instance.


