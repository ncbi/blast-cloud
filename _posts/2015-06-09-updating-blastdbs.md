---
layout: page
category: blastdb
title: "Updating BLAST databases"
order: 1
---

Users may want to install other databases from the [NCBI FTP site](ftp://ftp.ncbi.nlm.nih.gov/blast/db) using the
`update_blastdb.pl` program. First, [log in to your running
instance via ssh]({{site.baseurl}}{% post_url 2015-06-09-running-blast %}) and run the
commands below :

    cd /blast/blastdb_custom
    update_blastdb.pl --decompress --passive <dbname>
    # Can also scp and install your own BLAST databases in this directory

These (and any other) BLAST databases installed in the `/blast/blastdb_custom`
directory in the instance will be immediately available for searching via the
URL API, web interface, and BLAST+ command line applications on that instance.

*Note*: To update the [available BLAST databases]({{site.baseurl}}{% post_url 2015-06-09-available-blastdbs %}), please run the two commands listed in the
[fuse client]({{site.baseurl}}{% post_url 2015-06-09-fuse %}) page *when there are no BLAST searches running on your instance*.

If you run into any difficulty, please feel free to email us at blast-help@ncbi.nlm.nih.gov so we can help you!
