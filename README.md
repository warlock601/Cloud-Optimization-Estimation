# Cloud-Cost-Optimization-And-Estimation

To calculate total cost of the infrastructure. This is something why Small-scale and mid-scale startups show interest in public cloud, because there is no overhead in estimating cost of the built infrastructure. Let say the Management has asked DevOps engineer to build the infrastructure, then if the ewngg build the infrastructure thats not only it as the organization will benifit only if the infrastructure built is cost-optimized. <br/>
Common Example: Let say a Developer has IAM permissions for EC2, EBS, S3 & so he created an EC2 instance and took backups/snapshots of the EBS volume attached and stored the snapshots in an S3 bucket and then forgot to delete those after use, so AWS will keepo charging for the bucket and the team will not know about this or Let say he created an EBS volume & forgot to attach this volume to any of the EC2 instance. This is where a devops engg can notice this & let the team know and optmize the cost.<br/>
There are almost 200 resources in AWS and to manually monitor all these resources is not feasible. So the Devops engg should check whether there are any Stale resources & if there are 2 things what needs to be done:
- Send Notifications using SNS to the concerned people.
- Delete the resources if not needed.

So here we'll see how Devops engg can optmizew cost by deleting the resources that are no longer needed.<br/>

### Problem Statement: 
There are some EBS Volume snapshots & There is an EC2 instance and it has an EBS volume attached to it by default & the developer created multiple snapshots for that volume to preserve data and later the EC2 instance was deleted but the Snapshots and Volumes were not deleted. No one is using those snapshots hence they're useless. So, we need to delete them.


### Process Walkthrough:
- A Lambda function in python which will talk to the AWS API
- Using this Lambda function, we Fetch all the EBS Snapshots and Filter out the snapshots that are stale
- Delete stale snapshots (Stale here refers to the snapshots for which the volumes are deleted or those snapshots for wehich volumes exist but are not attached to any EC2 instance)



