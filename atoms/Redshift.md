### Summary of Redshift
Amazon Redshift uses SQL to analyze structured and semi-structured data across data warehouses, operational databases, and data lakes, using AWS-designed hardware and machine learning to deliver the best price performance at any scale. #AWSService 
### Redshift Details
* Data warehouse: data storage solution with historical data from disparate sources.
* Business intelligence, querying and business intelligence.
* Handles exabyte-scale data. OLAP implementation based on PostgreSQL engine.
> #UseCase 
	Data consolidation. Run a database when it doesn't require CRUD.
	Analytics - allows querying to gain business insights.
	Faster queries, data aggregation due to ability to index as compared to [[Athena]].

> #Q How to isolate from public Internet?
Enhanced VPC Routing allows you to use Amazon VPC Endpoints and VPC security groups to control access to your Redshift clusters. With Enhanced VPC Routing, all COPY and UNLOAD traffic is routed through the Amazon VPC and can be isolated from the public internet. This can help improve security and compliance, and reduce the risk of data exfiltration or unauthorized access. #secure 

> Default Standard Internet Routing
By default, Amazon Redshift uses standard Internet routing for COPY and UNLOAD traffic, which can bypass your VPC and traverse the public internet. Enhanced VPC Routing ensures that all traffic between your cluster and data repositories stays within your VPC, providing an additional layer of protection and control. #secure 


> #Q How to prepare Redshift for [[DR]] ?
>  Use automated snapshots to another region. 
> There is a multi-AZ option now available too. #resilient 
> 	![[Pasted image 20230314170257.png|256]]
#### References for Redshift
1. [RedShift](https://aws.amazon.com/redshift/)

---
Created on 2023-03-14 16:55
