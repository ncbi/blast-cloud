---
layout: page
category: usage
title: "Stopping an instance"
order: 1
---

**NOTE 1**: _Stoppage_ allows the instance to be stopped and re-started at a later time. Any previously computed BLAST results will still be available once the instance is re-started. AWS will only charge a small fee for storage of the data in an EBS volume.

**NOTE 2**: Stopping an instance will **delete** any of the [available BLAST databases]({{site.baseurl}}{% post_url 2015-06-09-available-blastdbs %}) that were already downloaded. When the instance is re-started, the [BLAST databases]({{site.baseurl}}{% post_url 2015-06-09-available-blastdbs %}) will be downloaded on demand.

1. Login to the [AWS console](https://console.aws.amazon.com/ec2).
**NOTE 3**: _Termination_ of instance is permanent, all data stored in the instance is lost forever.<br>

**WARNING**: You may want to download your BLAST results before **terminating** the instance, as once this is done, all the contents of the instance will be lost.


2. Identify the instance you would like stop **OR** terminate (tip: use the instance ID as a means to filter the listing of running instances).
![EC2 filter by IID](../images/ec2-filter-by-iid.png "EC2 filter by IID")

3. Click on 'Actions -> Instance State -> Stop' **OR** 'Actions -> Instance State -> Terminate'.
![EC stop terminate](../images/ec2-stop-terminate.png "EC stop terminate")

4. Confirm the Stop (4a) **OR** termination(4b).
![4a](../images/ec2-stop-confirm.png "4a")4a
![4b](../images/ec2-termination-confirm.png "4b")4b

