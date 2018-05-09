---
layout: page
category: doc
title: "Intended Audience"
order: 0
---

The NCBI BLAST AMI will be useful to a variety of users. The requirements for
using it and how easy it will be to set up will depend on the user's workflow
and the level of expertise with setting up computing resources on a cloud
service provider.

For those without a background in computers, having familiarity with cloud
services is helpful, but not mandatory, as the AWS Marketplace provides a
1-Click-Launch option and documentation on how to start/stop your instances. 
If you run into any difficulty, please feel free to email us at
blast-help@ncbi.nlm.nih.gov so we can help you!

A typical scenario would be to have one user in a group/team to register at a cloud
provider, configure the instance, and handle payment for the running
instance(s). Other members of the group/team can then use the instance through the 
[Common URL API]({{site.baseurl}}{% post_url 2015-06-09-api %}) or [webpage]({{site.baseurl}}{% post_url 2015-06-09-running-web-blast %})
without their own cloud provider account. The Common URL API interface
is ideal for users familiar with the BLAST URL API at the NCBI. Currently, the
BLAST server image runs searches on only one instance. Many simultaneous users,
could overload a single instance, to avoid this [monitor your instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring-system-instance-status-check.html).

Please see the table below for specific examples:

| Task/workflow | 1-click-start | Knowledge of ssh/scp/networking| Optimal data center region| Programmatic access via [Common URL API]({{site.baseurl}}{% post_url 2015-06-09-api %})|
|---------------|---------------|---------------------------------|------------------------|--------------------|
|BLAST against protein nr, swissprot, <br>refseq_protein, pdbaa, or <br>nucleotide nt, pdbnt, refseq_rna via web interface|Yes (1) |Limited (4)| us-east-1 (N. Virginia)| Not applicable|
|BLAST your own/propietary sequence data (2,3) |Limited options|Required (4)|Closest to where your data is *stored*|Optional|
|Third party application developers to run BLAST (3)|Limited options|Required (4)|Depends on user's workflow (see two rows above)|Likely required|

##### Foot notes

1. The 1-Click-Launch options is configured by default to start a large enough instance to run searches against the nr and nt BLAST databases and store the results in the instance's local disk.
2. For those users with proprietary sequence data, you can convert that sequence data into BLAST databases and [upload the resulting BLAST databases to a running instance]({{site.baseurl}}{% post_url 2015-06-09-updating-blastdbs %}).
3. Please be sure to [choose an appropriately sized instance]({{site.baseurl}}{% post_url 2015-06-09-choosing-instance %}) for your workload.
4. Please see [setting up remote access]({{site.baseurl}}{% post_url 2015-06-09-setting-up-remote-access %}).
