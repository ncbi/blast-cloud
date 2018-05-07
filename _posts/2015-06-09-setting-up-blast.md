---
layout: page
category: doc
title: "Setting up remote access"
order: 9
---

If you wish to allow remote searches, then you will need to enable HTTP access
when you configure your instance *and* provide [authentication]({{ site.baseurl }}{% post_url 2015-06-09-authentication %})
(please see [Running Web BLAST]({{ site.baseurl }}{% post_url 2015-06-09-running-web-blast %}) and
[Common URL API]({{ site.baseurl }}{% post_url 2015-06-09-api %})). If you allow HTTP access, it is very important that you
configure your security group/network firewall properly. If the group is not restricted, anyone
with knowledge of your public DNS may perform remote searches on your instance,
see all the BLAST results for remote searches or delete the results. If
possible, you should configure the security group/network firewall of your instance to
allow HTTP access only from a specific set of IP's (e.g. your lab's network). You should
also only share the public DNS of your instance with people who have your
permission to use it.

As a security precaution, the BLAST AMI blocks all ports but 22 and 80.
The BLAST results are kept on ephemeral storage. They will disappear when the
instance is stopped or terminated. If you wish to keep them, then you should
move them to permanent storage at your cloud provider or your institution.
