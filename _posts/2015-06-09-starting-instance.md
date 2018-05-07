---
layout: page
category: doc
title: "Starting an instance"
order: 2
---

An account is required with Amazon Web Services (AWS). As cloud providers rapidly change their product offerings, please consult their cloud documentation first.

1. Go to the [NCBI BLAST home page](https://blast.ncbi.nlm.nih.gov) and click on "Use BLAST in the cloud".
![BLAST home page](../images/blast-home-cloud.png "BLAST home page")

2. Click on the [AWS marketplace link](https://aws.amazon.com/marketplace/pp/B00N44P7L6).
![BLAST AMI link](../images/blast-home-mktplace-link.png "BLAST AMI link")

3. Click on "Continue to subscribe".
![BLAST AMI Marketplace](../images/aws-mktplace-ami-page.png "BLAST AMI Marketplace")

4. Login with your AWS credentials (requires sign up and credit card information).
![Marketplace Sign In](../images/aws-mktplace-sign-in.png "Marketplace Sign In")

5. Single click launch via yellow button (see area with a red circle in screenshot below). Machine type can be changed using the area highlighted in green (see 2nd screenshot below and adjusted hourly price).
![Single Click launch](../images/aws-mktplace-launch-single-click.png "Single Click launch")
![single click non default](../images/aws-marketplace-non-default-machine-type.png "Single Click non default")

:warning: If end user wants to login to the machine via ssh, please be sure to set the proper Key Pair to enable access. If this is not needed, no worries, you can still access the web application via the web browser.

6. A confirmation page will follow, to get the URL of your instance, follow the "Console" link (highlighted below). This is also accessible via https://console.aws.amazon.com/ec2/ .
![Marketplace confirmation](../images/aws-marketplace-confirmation.png "Marketplace confirmation")

7. In the AWS console, follow the link to "Running Instances".
![console running instances](../images/aws-console-running-instances.png "console running instances")

8. Identify your running instance. One way of achieving this is as follows:
  1. Sort the instances by descending launch time (newest first); as it is likely that yours will be at/near the top.
  1. Copy the public DNS for the machine _and the instance ID.
![console public dns](../images/ec2-console-public-dns.png "console public dns")

9. Paste the public DNS into your web browser.
![AMI authentication](../images/ami-authentication.png "AMI authentication")

10. Click on "BLAST QUERY" and in the "Sign in" window enter the user name 'blast' and for password use the instance ID from the previous step:
![AMI authentication Sign in](../images/ec2-ami-authenticate.png "AMI authentication Sign in")

11. Run BLAST to your heart's content :smiley:
![AMI home page](../images/ami-home-page.png "AMI home page")



