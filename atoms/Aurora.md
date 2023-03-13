## Aurora Summary
Aurora is a Cloud Optimized RDS. It is HA out of the box with read scaling, as well as offers global reads and serverless. The underlying storage volume automatically grows. #AWSService 
## About
Writer, Reader and Custom endpoints provide flexibility, scale and high availability.
- 6 copies of your data across 3 AZs.
- Storage striped across 100s of volumes.
- Up to 15 read-only replicas in different AZs and Regions (with supported database)
- Reader Endpoint can auto scale by adding additional replicas to service.
- Writer Endpoint points to the primary server.
- Custom Endpoints can point to a cluster of more powerful replicas e.g. for analytical queries. You would typically define various endpoints for different read workloads.
- Underlying shared volume spans Writer and Reader Endpoints - auto expands from 10GB to 128TB.
- Automated patching with zero downtime. Advanced monitoring.
- Backtrack: restore data at any point of time without using backups.
### Serverless
- Aurora Serverless has a pay-as-you-go model
### Multi-Master
- Every node does Read-Write to enable immediate failover.
### Global
* Read Replicas 
	* This set up is to enable DR by creating a read-replica in another region.
* Global Database
	* 1 Primary Region (Read and Write).
	* Up to 5 secondary Regions (Read-Only).
	* Replication lag is 1 second!
	* Promoting another region : [[RTO]] < 60 seconds.
### Machine Learning
-  Amazon [[SageMaker]] and Amazon [[Comprehend]]
- Fraud detection, ads targeting, sentiment analysis, product recommendations. #UseCase 
## References

1. https://aws.amazon.com/rds/aurora/