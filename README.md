# SAA-C03 Overview
The SAA focus : `The focus of this certification is on the design of cost and performance optimized solutions, demonstrating a strong understanding of the AWS Well-Architected Framework.`

The following are the various resources for gaining knowledge, learning the skills and testing resources to succeed in the Solutions Architect Associate examination. 
![AWS](https://d1.awsstatic.com/training-and-certification/certification-badges/AWS-Certified-Solutions-Architect-Associate_badge.3419559c682629072f1eb968d59dea0741772c0f.png)
## Domains
Design Architectures that are:
1. Secure 0.30
2. Resilient 0.26
3. High-Performing 0.24
4. Cost-Optimized 0.20

### 1. Secure

1. Design secure access to AWS resources.
	1. Access controls and management across multiple accounts.
	2. AWS federated access and identity services. AWS Identity and Access Managment (IAM), AWS Single-Sign-On.
	3. AWS [[Global Infrastructure]] (AZ, AWS Regions).
	4. AWS Security Best Practices (e.g. Principle of Least Privilege).
	5. The AWS Shared Responsibility Model.
	2. Skills
		1. Applying AWS security best practices to [[IAM]] users and root users (for example, multifactor authentication [[MFA]])
		2. Designing a flexible [[authorization]] model that includes [[IAM]] users, groups, roles and policies.
		3. Designing a security strategy for multiple AWS accounts (for example, [[AWS Control Tower]], Service Control Policies [[SCP]]).
		4. Determine the appropriate use of resource policies for AWS services.
		5. Determining when to [[federate]] a [[directory service]] with [[IAM]] roles.
2. Design secure workloads and applications.
	1. Application configuration and credentials security.
	2. AWS service endpoints.
	3. Control ports, protocols, and network traffic on AWS.
	4. Secure application access.
	5. Security services with appropriate use cases (for example, Amazon Cognito, Amazon Guard Duty, Amazon Macie).
	6. Threat vectors external to AWS (for example, DDoS, SQL injection)
	2. Skills:
		1. Designing VPC architectures with security components (for example, security groups, route tables, NACL, NAT gateways).
		2. Determining network segmentation strategies (for exampe, using public subnets and private subnets).
		3. Integrating AWS services to secure applications (for example, AWS Shielf, AWS WAF, AWS SSO, AWS Secrets Manager).
		4. Securing external network connections to and from the AWS Cloud (for example, VPN, AWS Direct Connect).
		
1. Determine appropriate data security controls.
	1. Knowledge:
		1. Data aacess and governance.
		2. Data recovery.
		3. Data retention and classification.
		4. Encruption and appropriate key management.
	2. Skills:
		1. Aligning AWS technologies to meet compliance requirements.
		2. Encrypting data at rest (for example, AWS Key Management Service [[KMS]])
		3. Encrypting data in transit (for example, AWS Certificate Manager [[ACM]] using TLS)
		4. Implementing access policies for encryption keys.
		5. Implementing data backups and replications.
		6. Implementing policies for data access, lifecycle, and protection.
		7. Rotating encryption keys and renewing certificates.
		8. 
### 2. Resilient
1. Design scalable and loosely coupled architectures
	1. API creation and management : API Gateway, REST API
	2. AWS managed services with appropriate use cases: AWS Transfer Family, Amazon SQS, Secrets Manager.
	3. Caching Strategies
	4. Design principles for microservices: stateless workloads compared with stateful workloads.
	5. Event-driven architectures.
	6. Horizontal scaling and vertical scaling.
	7. How to appropriately use edge accelerators: CloudFront CDN.
	8. Load Balancing Concepts. 
	9. Multi-tier architectures.
	10. Queuing and messaging concepts: publish-subscribe.
	11. Serverless technologies and patterns: AWS Lambda and AWS Fargate.
	12. Storage types with associated characteristics: Object, File, Block.
	13. The orchestration of containers: ECS, EKS.
	14. When to use read replicas.
	15. Workflow orchestration: AWS Step Functions.
	16. Skills:
		1. Designing event-driven, microservices, and multi-tier architectures based on requirements.
		2. Determining scalaing strategies for components used in an architectural design.
		3. Determining the AWS services for components used in an architecture design.
		4. Determining the AWS services required to achieve loose coupling based on requirements.
		5. Determining when to use containers.
		6. Determining when to use serverless technologies and patterns.
		7. Recommending appropriate compute, storage, networking, and database technologies based on requirements.
		8. Using purpose-built AWS services for workloads.
2. Design highly available and fault tolerant architectures 
	1. AWS [[global infrastructure]]: AZ, Regions, Route 53.
	2. AWS managed services with appropriate use cases: Comprehend, Polly.
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
### 3. High Performing
1. Determine high-performing and scalable storage solutions.
	1. Hybrid storage solutions to meet business requirement.
	2. Storage services with appropriate use cases: S3, EFS, EBS.
	3. Storage types with associated characteristics: Object, File, Block.
	4. Skills:
		1. Determining storage services and configurations that meet performance demands.
		2. Determining storage services that can scale to accomodate future needs.
2. Design high-performing and eslastic compute solutions.
	1. AWS compute services with appropriate use cases: AWS Batach, EMR, Fargate.
	2. Distributed computing concepts supported by AWS [[global infrastructure]] and edge services.
	3. Queuing and messaging concepts: Pub-sub.
	4. Scalability capabilities with appropriate use cases: [[EC2 Auto Scaling]] AWS Auto Scaling.
	5. Serverless technologoes and patterns: Lambda, Fargate.
	6. Orchestration of containers: ECS, EKS.
	7. Skills:
		1. Decoupling workloads so that components can scale independently.
		2. Identifying metrics and conditions to perform scaling actions.
		3. Selecting the appropriate compute options and features.
		4. Selecting the appropriate resource type and size (Lambda) to meet business requirements.
3. Determine high-performing database solutions.
	1. Caching strategies and services: ElastiCache.
	2. Data access patterns: Read-intensive compared to write-intensive.
	3. Database capacity planning: Capacity Units, Instance Types, Provisioned IOPS.
	4. Database connections and proxies.
	5. Database engines with appropriate use cases: Hetreogeneous migrations, homogenous migration.
	6. Database replication: Read replicas.
	7. Database types and services: Serverless, relational, non-replantion and in-memory.
	8. Skills:
		1. Configuring read replicas to meet business requirements.
		2. Designing database architectures.
		3. Determining an appropriate database engine: MySQL compared with PostgreSQL.
		4. Determining an appropriate database type: Auroro, DynamoDB.
		5. Integrating caching to meet business requirements.
4. Determined high-performing and scalable network architectures.
	1. Edge networking services weith appropriate use cases: Cloud Front, Global Accelerator.
	2. How to design network architecture: Subnet tiers, routing, IP addressing.
	3. Load balancing concepts: Application Load Balancer [[ALB]]
	4. Network connection options: AWS VPN, Direct Connect, AWS PrivateLink.
	5. Skills:
		1. Creating a network topology for various architecture: Global, Hybrid, Multi-tier.
		2. Determining network configurations that can scale to accomodate future needs.
		3. Determining the appropriate placement of resoureces to meet business requirements.
		4. Selecting the approrpriate load balancing strategy.
5. Determine high-performing data ingestion and transformation solutions.
	1. Data analytics and visualization services with appropriate use cases: Amazon Athena, Lake Formation, QuickSight.
	2. Data ingestion patterns.
	3. Data transfer services with appropriate use cases: AWS DataSync, AWS Storage Gateway.
	4. Data transformation services with appropriate use cases: AWS Glue.
	5. Secure access to ingestion access points.
	6. Sizes and speeds needed to meet business requirements.
	7. Streaming data services with appropriate use cases: Amazone Kinesis.
	8. Skills:
		1. Building and securing data lakes.
		2. Designing data streaming architectures.
		3. Designing data transfer solutions.
		4. Implementing visualization strategies.
		5. Selecting appropriate compute options for data processing: Amazone EMR.
		6. Selecting appropriate configurations for ingestion.
		7. Transforming data between formats: CSV to Parquet.
### 4. Cost Optimized
1. Design cost-optimized storage solutions.
	1. Access options: S3 with Requester Pays object storage.
	2. AWS cost management service features: Cost Allocation Tags, Multi-Account billing.
	3. AWS Cost Management tools with appropriate use cases: AWS Cost Explorer, AWS Budgets, AWS Cost and Usage Report.
	4. AWS storage services with appropriate use cases: Amazon FSx, Amazon EFS, Amazon S3, Amazon EBS.
	5. Backup strategies.
	6. Block storage options: HDD volume types, SSD volume types.
	7. Data lifecycles.
	8. Hybrid storage options: DataSync, Transfer Family, Storage Gateway.
	9. Storage access patterns.
	10. Storage tiering: Cold Tiering for object storage.
	11. Storage types with associated characteristics: Object, File and Block.
	12. Skills:
		1. Designing appropriate storage strategies: Batch uploads to AWS S3 compared with individual uploads.
		2. Determining the correct storage size for a workload.
		3. Determining the lowest cost method of transferring data for a workload to AWS storage.
		4. Determining when storage auto scaling is required. 
		5. Managing S3 object lifecycles.
		6. Selecting the appropriate backup and archival solution.
		7. Selecting the appropriate services for data migration to storage services
		8. Selecting the appropriate storage tier
		9. Selecting the correct data lifecycle for storage.
		10. Selecting the mnost cost-effective storage service for a workload.
2. Design cost-optimized compute solutions.
	1. AWS cost management service features: Cost Allocation Tags, Multi-Account Billing.
	2. AWS Cost Management tools with appropriate use cases: Cost Explorer, AWS Budgets, AWS Cost and Usage Report.
	3. AWS [[global infrastructure]]: Availability Zone, Regions.
	4. AWS purchasing options: Spot Instances, Reserved Instances, Savings Plans.
	5. Distributed compute strategies: Edge processing.
	6. Hybrid compute options: AWS Outposts, Snowball Edge.
	7. Instance types, families, and sizes: Memory optimized, compute optimized, virtualization.
	8. Optimization of compute utilization: [[Containers]], [[Serverless]] computing, [[Microservices]].
	9. Scaling strategies: Auto scaling, hibernation.
	10. Skills:
		1. Determining an appropriate load balancing strategy: ALB (Layer 7) , Network Load Balancer (Layer 4) compared with Gateway Load Balancer.
		2. Determining appropriate scaling methods and strategies for elastic workloads (Horizontal compared with Vertical, EC2 Hibernation).
		3. Determining cost-effective AWS compute services with appropriate use cases: Lambda, EC2, Fargate.
		4. Determining the required availability for different classes of workloads: production workloads, non-production workloads.
		5. Selecting the appropriate instance family and size for a workload.
3. Design cost-optimized database solutions.
	1. AWS cost management service features: Cost Allocation Tags, Multi-Account Billing.
	2. AWS Cost Management tools.
	3. Caching Strategies.
	4. Data retention policies.
	5. Data capacity planning.
	6. Data connections and proxies.
	7. Database engines with appropriate use cases: heterogenouse migrations, homogenous migrations.
	8. Database replication: read replicas.
	9. Database types and services: relational compares with non-relational, Aurora, DynamoDB.
	10. Skills:
		1. Designing appropriate backup and retention policies: snapshot frequency.
		2. Determining an appropriate database engine: MySQL versus PostGres.
		3. Determining cost-effective AWS database services with appropriate use cases: DynamoDB compares with Amazon RDS, serverless.
		4. Determining cost-effective AWS database type: time series format, columnra format.
		5. Migrating database schemas and data to different locations and different database engines.
		   
1. Design cost-optimized network architectures.
	1. AWS cost management service features and tools.
	2. Load balancing concepts: ALB.
	3. NAT gateways: NAT instnace costs compared with NAT gateway costs.
	4. Network connectivity: Private lines, dedicated lines, VPNs.
	5. Network routing, topology, and peering: AWS Transit Gateway, VPC peering.
	6. Network services with appropriate use cases: DNS.
	7. Skills:
		1. Configuring appropriate NAT gateway types for a network: Single shared NAT gateway compared with NAT gateways for each AZ.
		2. Configuring appropriate network connections: Direct Connect compared with VPN compared with Internet.
		3. Configuring appropriate network routes to minimize transfer costs: Region to Region, AZ to AZ, private to public, Global Accelerator, VPC endpoints.
		4. Determining strategic needs for content delivery networks and edge caching.
		5. Reviewing existing workloads for network optimizations.
		6. Selecting an appropriate throttling strategy.
		7. Selecting the appropriate bandwidth allocation for a network device: single VPN compared with multiple VPN, Direct Connect speed.



[AWS Whitepapers](00-Resources/AWS Whitepapers.md)
1. Exam Guide: [Click Here](https://d1.awsstatic.com/training-and-certification/docs-sa-assoc/AWS-Certified-Solutions-Architect-Associate_Exam-Guide.pdf)

### Video Coursework 
