---
layout: page
category: blastdb
title: "Custom BLAST databases"
order: 2
---

After you have [created your own BLAST
databases](https://www.ncbi.nlm.nih.gov/books/NBK279688/), to make them
available in the BLAST AMI, simply copy your BLAST database files onto the
instance's `/blast/blastdb_custom` directory. E.g.:

    scp -i <PATH_TO_YOUR_PEM_OR_SSH_KEY_FILE> <BLASTDB_FILES> ubuntu@<YOUR_INSTANCES_DNS>:/blast/blastdb_custom/


These (and any other) BLAST databases installed in the `/blast/blastdb_custom`
directory in the instance will be immediately available for searching via the
URL API, web interface, and BLAST+ command line applications on that instance.


**If you run into any difficulty, please feel free to email us at blast-help@ncbi.nlm.nih.gov so we can help you!**
