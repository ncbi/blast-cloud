---
layout: page
category: usage
title: "Running Web BLAST"
order: 3
---
To run WebBLAST on the instance you [started at AWS]({{ site.baseurl }}{% post_url 2015-06-09-starting-instance %}), simply point your web browser at the Public DNS of your instance with the suffix `cgi-bin/blast.cgi`:

**Note**: You will need to [authenticate]({{ site.baseurl }}{% post_url 2015-06-09-authentication %}) the first time you access this URL.

![BLAST submission page](../images/submissionscreenshot.png "BLAST submission page")


By clicking on the 'Recent Results' tab near of the top of the page you will be able to see the BLAST searches that have run on this instance, their status, and access their results:

![BLAST recent results page](../images/rid-listing-screenshot.png "BLAST recent results page")
