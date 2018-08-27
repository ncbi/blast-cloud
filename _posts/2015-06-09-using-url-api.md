---
layout: page
category: dev
title: "Using the Common URL API"
order: 1
---
This page describes how to use the [NCBI-BLAST Common URL API]({{ site.baseurl }}{% post_url 2015-06-09-api %}) to run remote BLAST searches.  These instructions assume you are running searches at a cloud provider, but minor modifications
allow you to run searches at the NCBI web server.  A note at the bottom of this page provides information on searches at the NCBI.

To run a search, you should:

1. Launch a BLAST instance. The security group must allow access through HTTP.
   If possible, restrict the allowed IP's for HTTP so as to include only those
   of the intended users. See [setting up remote access]({{site.baseurl}}{% post_url 2015-06-09-setting-up-remote-access %}) and your cloud provider's documentation. The examples
   on this page assume Amazon Web Services (AWS).

1. Once the instance has launched, obtain the Public DNS from your cloud provider.
For AWS, the Public DNS will look like:
`http://ec2-54-82-43-97.compute-1.amazonaws.com` though the exact numbers and letters
will be depend upon your instance.

1. Launch a search using your Public DNS plus cgi-bin/blast.cgi. You will need to 
[authenticate]({{ site.baseurl }}{% post_url 2015-06-09-authentication %}) before submitting a search.
For the example Public DNS given above, a URL to search the sequence of accession
u00001 against nt would be:
`http://ec2-54-82-43-97.compute-1.amazonaws.com/cgi-bin/blast.cgi?QUERY=u00001&DATABASE=nt&PROGRAM=blastn&CMD=Put`

1. The server will respond with HTML containing a `QBlastInfo` block.  The QBlastInfo block will contain
a RID ("Request ID") that can be used to retrieve results as well as a RTOE that is an estimated time in seconds 
until the search is completed.  An example QBlastInfo block is:

    ```
    <!--QBlastInfoBegin
       RID = SYZDXEWK014  
       RTOE = 31  
    QBlastInfoEnd
    -->
    ```

1. You may check the status of the search by invoking blast.cgi with the parameters `CMD=Get`,
`FORMAT_OBJECT=SearchInfo`, and `RID=VALUE`, where `VALUE` is the `RID` returned by
the server.  The server will respond with a page containing a `QBlastInfo`
block with the status set as one of `WAITING`, `UNKNOWN`, or `READY`.

1. Once the search is finished, you may retrieve results by invoking blast.cgi
with the parameters `CMD=GET` and `RID=VALUE`, where `VALUE` is the `RID` the system
returned. An example would be "CMD=Get&RID=6NTRF1YLO8". You may also specify
the report type (e.g, add `FORMAT_TYPE=Text`).

**Note**: If you have not restricted your security group, anybody
with knowledge of your public DNS can use `CMD=DisplayRIDs` to see all remote
searches available on the system.

**Note**: The BLAST server at the NCBI supports the same URL API.  At the NCBI, you should
use the URL https://blast.ncbi.nlm.nih.gov/Blast.cgi but follow the same basic procedure.  Naturally, you do not need to launch an instance first.  Note that only HTTPS is supported at the NCBI server after 09/30/2016.  The NCBI BLAST 
server is a shared resource and usage restrictions may apply.  See information 
[here](https://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Web&PAGE_TYPE=BlastDocs&DOC_TYPE=DeveloperInfo).
