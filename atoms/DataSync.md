### Summary of DataSync
Synchronize large amounts of data, and meta-data to and from on-prem or other cloud to AWS with NFS, SMB, HDFS, S3 and [[FIPS]] endpoints on a schedule.
### Summary of DataSync

### DataSync Details

#### References for DataSync
1.

---
Created on 2023-03-09 17:09
### DataSync Details
- Schedule data transfers between:
	- On-Prem and AWS
	- AWS Services
	- AWS and other Cloud
![Agent|350](Pasted%20image%2020230309165809.png)
- One agent task can use 10 Gbps. Throttle bandwidth to preserve other workloads #BestPractice 
- Useful if you need the file permissions and metadata are preserved. It copies the data and meta-data. #UseCase 
- Do not use DataSync if you have bandwidth issues, instead opt for [Snowcone](Snow%20Family.md#Snowcone) that comes pre-installed with the DataSync agent. #BestPractice 
![](Pasted%20image%2020230309170808.png)
#### References for DataSync
1. https://aws.amazon.com/datasync/faqs/

---
Created on 2023-03-09 16:43