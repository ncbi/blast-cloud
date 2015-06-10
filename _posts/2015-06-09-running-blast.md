---
layout: page
category: doc
title: "Running BLAST"
order: 1
---
Users familiar with command line interfaces can run the [BLAST+
applications](http://www.ncbi.nlm.nih.gov/books/NBK1763) directly on their AWS
EC2 instance by logging on via ssh and issuing commands at the terminal prompt.
The BLAST AMI uses Ubuntu LINUX, so you should use the user name `ubuntu`
rather than `ec2-user` for the ssh connection.
The BLAST AMI already has the BLAST+ applications installed and will retrieve
the databases listed earlier upon demand. Additionally, users may manually
download other databases from the NCBI FTP site using the `update_blastdb.pl`
program as follows:

    cd /blast/blastdb_custom
    update_blastdb.pl --decompress --passive <dbname>

These (and any other) BLAST databases installed in the `/blast/blastdb_custom`
directory in the AWS instance will be immediately available for searching via
the URL API, web interface, and BLAST+ command line applications on that
instance.
