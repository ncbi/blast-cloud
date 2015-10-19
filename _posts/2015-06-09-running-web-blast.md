---
layout: page
category: doc
title: "Running Web BLAST"
order: 2
---
To run a search, you should:

1. Launch a BLAST instance. The security group must allow access through HTTP.
   If possible, restrict the allowed IP's for HTTP so as to include only those
   of the intended users. See your cloud provider's documentation. The examples
   on this page assume Amazon Web Services (AWS).

1. Once the instance has launched, obtain the Public DNS from your cloud provider.
For AWS, the Public DNS will look something like:
`ec2-54-82-43-97.compute-1.amazonaws.com` though the exact numbers and letters
will be depend upon your instance.

1. Launch a search using your Public DNS plus cgi-bin/blast.cgi. For the
example Public DNS given above, a URL to search the sequence of accession
u00001 against nt would be:
`ec2-54-82-43-97.compute-1.amazonaws.com/cgi-bin/blast.cgi?QUERY=u00001&DATABASE=nt&PROGRAM=blastn&CMD=Put`

1. The instance will return a "Request ID" (`RID`). You may check the status of
the search by invoking blast.cgi with the parameters `CMD=Get`,
`FORMAT_OBJECT=SearchInfo`, and `RID=VALUE`, where `VALUE` is the `RID` returned by
the server.  The server will respond with a page containing a `QBlastInfo`
block with the status set as one of `WAITING`, `UNKNOWN`, or `READY`.

1. Once the search is finished, you may retrieve results by invoking blast.cgi
with the parameters `CMD=GET` and `RID=VALUE`, where `VALUE` is the `RID` the system
returned. An example would be "CMD=Get&RID=6NTRF1YLO8". You may also specify
the report type, but need to include `FORMAT_OBJECT=Alignment` (e.g, add
`FORMAT_OBJECT=Alignment&FORMAT_TYPE=Tabular`).

_Note_: If you have not restricted your security group, please also note that anybody
with knowledge of your public DNS can use `CMD=DisplayRIDs` to see all remote
searches available on the system.
