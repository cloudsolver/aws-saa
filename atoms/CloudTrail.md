### Summary of CloudTrail
Governance, audit and compliance for your organization. #AWSService 
### CloudTrail Details
- CloudTrail records API calls made from any client. The AWS Management Console, AWS Software Development Kits (SDKs), command line tools, and higher-level AWS services call AWS API operations, so these calls are recorded.
- Per Region limit of 5 trails. 
- Each trail is 90 days retention by default. For longer retention move them to [[S3]] and use [[Athena]].
- Works with [[Config]] and [[CloudWatch]]
- #UseCase if any resource is deleted, always start the investigation with CloudTrail.

| Event Type                     | UseCase                                                                                       |
| ------------------------------ | --------------------------------------------------------------------------------------------- |
| Management Events (default on) | Operations on AWS resources e.g. `IAMAttachRolePolicy` can separate Read versus Write events. |
| Data Events (default off)      | S3 operations, Lambda operations etc. This is high volume.                                    |
| Insight                        | Creates a baseline and then alerts on anomalies e.g. gaps in periodic maintenance, bursts, service limits. ![[Pasted image 20230316131543.png]]                                                                                              |

*Note*: In order to log access to S3 bucket access. Data Events will need to be turned on.

> **Notification Architecture with CloudTrail**
> ![[Pasted image 20230316131732.png|512]] 
> Fig. DynamoDB table deletion sends an email via [[EventBridge]]
> EventBridge gets events automatically. 
---
> References for CloudTrail
1. https://aws.amazon.com/cloudtrail/faqs/ 

*Created on 2023-03-15 23:03*