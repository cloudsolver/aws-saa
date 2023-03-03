Amazon Machine Image are a customization of EC2 instance.
- Add your own software, config, OS, monitoring...
- #usecase pre-configured, faster initialization.
- AMI are build for specific region. #tip You can copy AMI across Regions.
- #Q You can use an AMI in N.Virginia Region us-east-1 to launch an EC2 instance in any AWS Region. True or False? Answer is false.

*Process fop creating an AMI*
Start an EC2 instance, customize it, stop the instance, build an AMI - this will create EBS snapshots: Launch instance.
