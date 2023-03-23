### Summary of ASG

### ASG Details
- Set desired, minimum and maximum capacity.
- Dynamic Scaling: Tracks [CloudWatch](CloudWatch) and acts when it is in ALARM.
	- Target Tracking Scaling: Amazon [[CloudWatch]] metric and target value.
	- Step Scaling: Update capacity based on a SET of scaling adjustments.
	- Simple Scaling: Update based on a SINGLE scaling adjustment. Cool down period.
ASG ensures EC2 instances are within a range (minimum, maximum capacity).
It can scale out EC2 instances to match the load, and scale in when load decreases.
Automatically registers new instances to a load balancer.
Recreate an EC2 instance if one is terminated or unhealthy.
There is no cost for ASG itself.
A Launch Template is required for an ASG.
	- [AMI](AMI.md) + Instance Type
	- EC2 User Data
	- EBS Volumes
	- Security Groups
	- [SSH](SSH.md) Key Pair
	- IAM Roles for EC2 Instances
	- Network + [[Subnet]] 
	- [ELB](ELB.md) Info
	- Initial Capacity, Min and Max Size.
	- Scaling Policies.
[[CloudWatch ]] Alarms can trigger a scaling request to ASG.
#### Quiz
#Q  You have an ASG and an [NLB](ELB.md#NLB). The application on your ASG supports the HTTP protocol and is integrated with the Load Balancer health checks. You are currently using the TCP health checks. You would like to migrate to using HTTP health checks, what do you do?
(a) Migrate to an Application Load Balancer
(b) Migrate the health check to HTTP
Answer: Both answers are correct. Remember, that NLB supports HTTP health checks.
#### References for ASG
1. https://docs.aws.amazon.com/autoscaling/ec2/userguide/scale-your-group.html

---
Created on 2023-03-10 21:55