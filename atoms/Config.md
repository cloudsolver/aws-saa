### Summary of Config
Configuration Auditor. Assess, audit, and evaluate  configuration of your resource. #AWSService 
### Config Details
- Use the AWS Management Console, API, or CLI to obtain details of what a resource’s configuration looked like at any point in the past. It is a per-Region service.
- AWS Config will also automatically deliver a configuration history file to the Amazon Simple Storage Service (S3) bucket you specify.
> **Config Rules**
	Specify configuration rules and be notified when configuration changes don't meet the rules.
	Implement Policies in the Config Rules engine to implement practice.

**Config Notification**

>**Config Remediation**
Remediation Architecture ![[Pasted image 20230316140950.png]]
> Create a custom [[SSM]] Document that triggers a Lambda function which takes the action.
> ![[Pasted image 20230316141153.png]]

- Config now support organization wide compliance view.
- Aggregate from multi-account multi-region out of the box. Integrates with AWS [[Organizations]]
- Does not prevent policy violations - only detects, audits and notifies.
- #UseCase  
	Is there unrestricted SSH access to my security groups?
	Do my buckets have any public access?
	How has my ALB configuration changed over time?


> 
> **References for Config**
1.  https://aws.amazon.com/config/features/
2. https://docs.aws.amazon.com/pdfs/config/latest/developerguide/config-dg.pdf
3. Multi-region, multi-account config: https://youtu.be/5m8ljOghcWM
4. https://docs.aws.amazon.com/systems-manager/latest/userguide/sysman-ssm-docs.html

---
*Created on 2023-03-15 23:03*