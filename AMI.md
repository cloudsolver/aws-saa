## Summary
Amazon Machine Image is a regional image that instantiates an EC2 instance.
## AMI Details
Amazon Machine Image are a customization of EC2 instance.
- Add your own software, config, OS, monitoring...
- #usecase pre-configured, faster initialization.
- AMI are build for specific [region](Region.md). #tip You can copy AMI across Regions.

*Process fop creating an AMI*
Start an [[EC2]] instance, customize it, stop the instance, build an AMI - this will create [[EBS]] snapshots: Launch instance.


![AMI Lifecycle](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/ami_lifecycle.png)
### Quiz 
- #Q You can use an AMI in N.Virginia [Region](Region.md) us-east-1 to launch an [[EC2]] instance in any AWS [[Region]]. True or False? 
- Answer is false.


## References

	1.https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html