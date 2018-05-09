---
layout: page
category: conf
title: "How to choose a region?"
order: 2
---

Since the [BLAST databases]({{site.baseurl}}{% post_url 2015-06-09-available-blastdbs %}) are fetched from the NCBI, downloads are faster if the
instance runs in a region that is geographically close to NCBI.

For AWS, `us-east-1` (N. Virginia) is the closest region, so for optimal download performance, please consider
starting your instance in that region. You can find a list of available AWS regions [here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html).

In other cases, such as `us-west-1` (N. California) and `eu-west-1` (Ireland), *downloading the BLAST databases can take a few hours*.

