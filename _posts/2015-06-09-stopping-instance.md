---
layout: page
category: doc
title: "Stopping an instance"
order: 6
---

**WARNING**: You may want to download your BLAST results before terminating the instance, as once this is done, all the contents of the instance will be lost.


1. Login to the [AWS console](https://console.aws.amazon.com/ec2).

2. Identify the instance to stop/terminate (tip: use the instance ID as a means to filter the listing of running instances).
![EC2 filter by IID](../images/ec2-filter-by-iid.png "EC2 filter by IID")

3. Click on "Actions -> Instance State -> Stop" or "Actions -> Instance State -> Terminate".
![EC stop terminate](../images/ec2-stop-terminate.png "EC stop terminate")
**NOTE**: Termination of instance is permanent, all data stored in the instance is lost forever.<br>
**NOTE**: Stoppage allows the instance to be re-started at a later time. Any previously computed BLAST results will still be available once the instance is re-started. AWS will only charge a small fee for storage of the data in an EBS volume.

4. Confirm the termination or stoppage.
![EC stop confirm](../images/ec2-stop-confirm.png "EC stop confirm")
![EC termination confirm](../images/ec2-termination-confirm.png "EC termination confirm")
