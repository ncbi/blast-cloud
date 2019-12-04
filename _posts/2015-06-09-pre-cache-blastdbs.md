---
layout: page
category: blastdb
title: "Pre-caching BLAST databases"
order: 5
---

One way to speed-up BLAST is to pre-load the BLAST database files into main
memory. In the case of BLAST databases retrieved by `remote-fuser`, this
pre-caching will trigger download of the database files on to local disk.

This can be achieved by running the command below on your instance:

    /usr/bin/cat ${PATH_TO_BLAST_DATABASE_FILES} >/dev/null
    
For instance, to pre-cache the nucleotide nt database files, please run the command:

    /usr/bin/ls /blast/blastdb/nt.*n{in,sq} | /usr/bin/xargs -P$(/usr/bin/grep -c ^processor /proc/cpuinfo) -t -I{} /usr/bin/cat {} >/dev/null

The command above sends the output of the `ls` command to `xargs` to execute
the `cat` command on multiple files in parallel.
