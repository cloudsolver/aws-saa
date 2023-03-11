## Summary
AWS offers four categorizes of EBS volumes: GP, IO, ST, and SC. GP is general purpose, IO is provisioned IOPS, ST is throughput optimized and SC is cold HDD volume.

Six types, grouped in 4 categories. Size, throughput and IOPS are differentiated.

## Volume Categories
### **gp2/gp3 (SSD) : General Purpose**

General purpose cost-effective low-latency SSD volumes.
#UseCase general workloads with a balance of price and performance. Boot volumes. Dev and test environment.
 gp3: 3K IOPS baseline and 125MiB/s. Increase 16 K IOPS and 1000 MiB/s (independent).
 gp2: 3K IOPS burst. IOPS and Size are linked: 3 IOPS per GB: 5334 GB maxes IOPS.
### **io1/io2 (SSD) : Fasted Provisioned IOPS**
	- Highest performance SSD volumes for mission critical and high-throughput workloads.
	- #UseCase Mission-critical low-latency or high-throughput workloads. Boot volumes.
	- io1 and io2 Size: 4GB-16TB. Max: 64K IOPS only for Nitro EC2; 32K IOPS for others. io2 is better than io 1 because you get more durability and more IOPS per GiB. #UseCase More than 32K IOPS with Nitro EC2.
	- io2 Block Express (4GiB - 64TiB) sub-second latency. Max IOPS: 256K GiB ratio 1000:1
	- #UseCase Multi-attach with full read/write: Same EBS volume to multiple EC2 instances in the same AZ. Up to 16 EC2 instances. Must use cluster-aware file system
	- #UseCase Achieve higher application availability in clustered Linux applications (e.g. Terradata). 
	- #UseCase Applications must manage concurrent write operations.
	
### st1 (HDD)
	- Low cost HDD vol. Cannot be boot volume.
	- #UseCase Frequent accessed, throughput sensitive. Big Data, Data Warehouses, Log Processing.
	- Size: 125 GiB to 16 TiB. Max IOPS 500 (500MiB/s)
### sc1 (HDD)
	- Lowest cost HDD vol. Cold HDD.
	- #UseCase Less frequently accessed. Archive data.
	- 250 IOPS max.

## References
- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/hdd-vols.html