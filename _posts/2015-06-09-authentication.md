---
layout: page
category: usage
title: "Web server authentication"
order: 3
---

In order to access [a running instance via a web browser]({{ site.baseurl }}{% post_url 2015-06-09-running-web-blast %}) 
or programmatically via the [NCBI-BLAST Common URL API interface]({{ site.baseurl }}{% post_url 2015-06-09-api %}), one
needs to provide credentials.

The user name is set to `blast` and the password is the AWS instance ID.

A web browser will prompt for credentials (see screenshot below); programmatic
access will require authentication to be configured. For example, assuming the instance's
ID is `i-01ef8ea68031299de` and its public DNS is `ec2-54-90-191-42.compute-1.amazonaws.com`:


```
$ curl http://blast:i-01ef8ea68031299de@ec2-54-90-191-42.compute-1.amazonaws.com/cgi-bin/blast.cgi
```


Please consult the appropriate tool/API's documentation to properly configure programmatic access.



![authentication screenshot](../images/ami-initialization.png "Authentication screenshot")

