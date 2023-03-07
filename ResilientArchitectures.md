## Resilient #resilient 
1. Design scalable and loosely coupled architectures
	1. API creation and management : [[API Gateway]], REST API
	2. AWS managed services with appropriate use cases: AWS Transfer Family, Amazon [[SQS]], [[Secrets Manager]].
	3. [[Caching]] Strategies
	4. Design principles for microservices: stateless workloads compared with stateful workloads.
	5. Event-driven architectures.
	6. Horizontal scaling and vertical scaling.
	7. How to appropriately use edge accelerators: CloudFront [[CDN]].
	8. Load Balancing Concepts. 
	9. Multi-tier architectures.
	10. Queuing and messaging concepts: publish-subscribe.
	11. Serverless technologies and patterns: AWS [[Lambda]] and AWS [[Fargate]].
	12. Storage types with associated characteristics: Object, File, Block.
	13. The orchestration of containers: [[ECS]], [[EKS]].
	14. When to use read replicas.
	15. Workflow orchestration: AWS Step Functions.
	16. Skills:
		1. Designing event-driven, microservices, and multi-tier architectures based on requirements.
		2. Determining scaling strategies for components used in an architectural design.
		3. Determining the AWS services for components used in an architecture design.
		4. Determining the AWS services required to achieve loose coupling based on requirements.
		5. Determining when to use containers.
		6. Determining when to use serverless technologies and patterns.
		7. Recommending appropriate compute, storage, networking, and database technologies based on requirements.
		8. Using purpose-built AWS services for workloads.
2. Design highly available and fault tolerant architectures 
	1. AWS [[global infrastructure]]: [[AZ]], Regions, Route 53.
	2. AWS managed services with appropriate use cases: [[Comprehend]], [[Polly]].
	3. Basic networking concepts: Route tables.
	4. Disaster Recovery strategies: Backup and restore, pilot light, warm standby, active-active failover, recovery point objective [[RPO]], recovery time objective [[RTO]]
	5. Distributed design patterns.
	6. Failover strategies.
	7. Immutable infrastructure.
	8. Load balancing concepts: ALB.
	9. Proxy concepts: RDS Proxy.
	10. Service quotas and throttling.
	11. Storage options and characteristicsd: Durability, replication.
	12. Workload visibility: AWS X-Ray.
	13. Skills:
			1. Determining automation stategies to ensure infrastructure integrity.
			2. Determining the AWS services requried to provide a highly available and fault-tolerant architecture across AWS Regions and AZ.
			3. Identifying metrics based on business requirements to deliver a highly available solution.
			4. Implementing designs to mitigate single points of failure.
			5. Implementing strategies to ensure the durability and availability of data.
			6. Selecting an appropriate DR strategy to meet business requirements.
			7. Using AWS services that improve the reliability of legacy applications and applications not built for the cloud.
			8. Using purpose-built AWS services for workloads.

### Availability
Availability quantitatively measure resiliency.