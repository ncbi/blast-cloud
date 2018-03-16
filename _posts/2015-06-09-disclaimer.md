---
layout: page
category: dev
order: 2
---

Although all reasonable efforts have been taken to ensure the accuracy and reliability of the software and data, The NLM and the U.S. Government do not and cannot warrant the performance or results that may be obtained by using this software or data. The NLM and the U.S. Government disclaim all warranties, express or implied, including warranties of performance, merchantability or fitness for any particular purpose.

There are a number of known issues and limitations to the approach described here.  They are listed below. 

There is no load balancing in the current AMI.  A number of users running searches at the same time could overload an instance. The NCBI hopes to address this in a future version.

It is possible that searches at an AWS instance could produce different results than those at the NCBI BLAST website.  The different results could be caused by differences in the version of the software, BLAST database, or other issues beyond the control of the NCBI.

A running instance will download BLAST databases from the NCBI.  The instance will normally place minimal demands on the NCBI website since the database is cached after the first download.  Use of an instance in a manner that places heavy demands on the NCBI site may result in the instance being blocked.

The BLAST results and databases are kept on ephemeral storage at AWS.  User error (e.g., premature stopping or termination of an instance) could result in loss of data.  Problems at AWS or with NCBI software could also result in the loss of data. 
