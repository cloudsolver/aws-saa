Elastic Block Storage is an attached #awsservice storage service for EC2; store up to 16 TiB and supply up to 64,000 IOPS.

It is locked to an Availability Zone (AZ). The volume and instance must be in the same AZ. In order to move the volume it needs to be snapshot first. Two EBS volumes can be attached to an EC2 instance in the same AZ.

The root EBS volume is deleted. #usecase You can preserve root volume when an instance is terminated but checking `preserve root volume on termination` 

### [[EBS Snapshots]]
#bestpractice detach the volume to do a snapshot. 

#### EBS Volume Types
Six types, grouped in 4 categories. Size, throughput and IOPS are differentiated.
- gp2/gp3 (SSD) : General Purpose
	- General purpose cost-effective low-latency SSD volumes.
	- #usecase general workloads with a balance of price and performance. Boot volumes. Dev and test environment.
	- gp3: 3K IOPS baseline and 125MiB/s. Increase 16 K IOPS and 1000 MiB/s (independent).
	- gp2: 3K IOPS burst. IOPS and Size are linked: 3 IOPS per GB: 5334 GB maxes IOPS.
- io1/io2 (SSD) : Provisioned IOPS
	- Highest performance SSD volumes for mission critical and high-throughput workloads.
	- #usecase Mission-critical low-latency or high-throughput workloads. Boot volumes.
	- io1 and io2 Size: 4GB-16TB. Max: 64K IOPS only for Nitro EC2; 32K IOPS for others. io2 is better than io 1 because you get more durability and more IOPS per GiB. #usecase More than 32K IOPS with Nitro EC2.
	- io2 Block Express (4GiB - 64TiB) sub-second latency. Max IOPS: 256K GiB ratio 1000:1
	- #usecase Multi-attach with full read/write: Same EBS volume to multiple EC2 instances in the same AZ. Up to 16 EC2 instances. Must use cluster-aware file system
	- #usecase Achieve higher application availability in clustered Linux applications (e.g. Terradata). 
	- #usecase Applications must manage concurrent write operations.
- st1 (HDD)
	- Low cost HDD vol. Cannot be boot volume.
	- #usecase Frequent accessed, throughput sensitive. Big Data, Data Warehouses, Log Processing.
	- Size: 125 GiB to 16 TiB. Max IOPS 500 (500MiB/s)
- sc1 (HDD)
	- Lowest cost HDD vol. Cold HDD.
	- #usecase Less frequently accessed. Archive data.
	- 250 IOPS max.
#### EBS Encryption
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
	
EBS restoration cannot be done to a size smaller, but you can restore to a larger file size.