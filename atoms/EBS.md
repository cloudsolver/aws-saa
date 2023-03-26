## Summary
Elastic Block Storage is an #AWSService attached storage service for EC2; store up to 16 TiB and supply up to 64,000 IOPS.
## Constraints
It is locked to an Availability Zone (AZ). The volume and instance must be in the same AZ. In order to move the volume it needs to be snapshot first. Two EBS volumes can be attached to an EC2 instance in the same AZ.

The root EBS volume is deleted upon termination. #UseCase You can preserve root volume when an instance is terminated but checking `preserve root volume on termination`  

## EBS Snapshots
![EBSSnapshots](EBSSnapshots.md#Summary)
#BestPractice detach the volume to do a snapshot. 
## EBS Volume Types
![EBS Volume Types](EBS%20Volume%20Types.md#Summary)
#Q What [[RAID]] types does AWS  recommend for EBS?
(a) RAID 0
(b) RAID 1
(c) RAID 5
(d) RAID 6
Answer: Amazon EBS volumes are placed in a specific Availability Zone where they are automatically replicated to protect you from the failure of a single component. All EBS volume types offer durable snapshot capabilities and are designed for 99.999% availability. Given that, AWS only recommends RAID 0. [Details](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/raid-config.html) 

### EBS Encryption
- Data at rest is encrypted.
- Data in flight between instance and volume is encrypted.
- All snapshots are encrypted.
- All volumes created from snapshot.
- Encryption and decryption are handled transparently with no intervention.
- KMS (AES-256).
- Encrypt Process:
	- Create an EBS snapshot of the volume.
	- Encrypt the EBS snapshot.
	- Copy the snapshot with encryption enabled.
	- Create new EBS volume from the snapshot.
	- Restore encrypted snapshot copy to volume.
	
