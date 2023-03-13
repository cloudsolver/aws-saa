Elastic File System #AWSService  - is a managed NFS - it can be mounted on many EC2 instances.
EFS works with EC2 instances in multi-AZ.
Highly Available, scalable expensive (3x gp2) - pay per use.
#UseCase CMS, Web Serving, Data Sharing, Wordpress
Uses NFSv4.1 protocol, Security Group to control access to EFS.
Compatible with Linux and not Windows: standard file API and POSIX.
Encryption at rest using KMS.
File-system will scale storage automatically.
Scale: 1000s of concurrent NFS clients, 10GB/second throughput
Storage: Petabyte-scale NFS
#### Performance Mode
- General Purpose : latency-sensitive use cases e.g. Web Server, CMS
- Max I/O: higher latency, high throughput, supports highly parallelized workloads. Very special use cases: media processing or higher latency.
#### Throughput Mode
- Bursting : 100MiBs, Elastic: scale based on workloads: #UseCase for unpredictable workloads.
- Provisioned/Enhanced: Set throughput regardless of storage size. 1 GiBs for 1 TB storage.
### Storage Class
- Standard: for frequently access files.
- IA: Lifecycle policy will trigger to move the file to a different tier. 90% savings
- One Zone and One Zone IA
	- Replaces data within a single AZ.
- Standard/Regional and Standard/Regional IA
	- Replicates data across multiple AZs.
