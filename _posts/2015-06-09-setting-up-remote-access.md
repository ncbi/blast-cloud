---
layout: page
category: conf
title: "Setting up remote access"
order: 1
---

If you wish to allow BLAST searches via a web browser, then you will need to enable HTTP access
when you configure your instance *and* provide [authentication]({{ site.baseurl }}{% post_url 2015-06-09-authentication %})
(please see [Running Web BLAST]({{ site.baseurl }}{% post_url 2015-06-09-running-web-blast %}) and
[Common URL API]({{ site.baseurl }}{% post_url 2015-06-09-api %})). By default,
the AMI enables these, so please read on.

In allowing HTTP access, it is very important that you
configure your security group/network firewall properly. If this is not restricted appropriately, anyone
with knowledge of your public DNS may perform remote searches on your instance,
see all the BLAST results for remote searches or delete the results. If
possible, you should configure the security group/network firewall of your instance to
allow HTTP access only from a specific set of IP's (e.g. your lab's network). You should
also only share the public DNS of your instance with people who have your
permission to use it.

As a security precaution, the BLAST AMI by default blocks all ports but 22 (for ssh) and 80 (for HTTP access).
