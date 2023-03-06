## Introduction
Amazon RDS is an #awsservice that is a managed DB service for RDBMS.
Supports
- PostgreSQL
- MySQL
- MariaDB
- Oracle
- Microsoft SQL Server
- Aurora 

## Features
- Automated provisioning, OS patching.
- Continuous backup on gb2 or io1 and Point-in-time restore.
- Monitoring Dashboards.
- Read replicas for improved read performance.
- Multi AZ setup for DR.
- Maintenance Windows for upgrades.
- Scaling capability vertical or horizontal.
### Storage Auto Scaling
- Scale storage automatically so the DB won't run out of free space.
- Set the `Maximum Storage Threshold`
- Useful for applications with _unpredictable workloads_.
- Automatically modify storage:
	- Free storage is <10% of allocated storage.
	- Low-storage lasts at least 5 mins.
	- 6 hours have passed since last modification.
## Constraints
- No SSH access to the database engine.


