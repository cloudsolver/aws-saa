Active Directory is supported by AWS. Directory Service #AWSService  


| AD Connector        | Simple AD          | Managed AD                                |
| ------------------- | ------------------ | ----------------------------------------- |
| Gateway Proxy to on-prem AD | No on-prem just AD | On-prem and AWS AD with trusted connection bilateral trust different accounts in AWS versus On-premise AD |
| Supports MFA        | No MFA             | MFA                                       |
|                     |                    |                                           |

With AD Connector users will be on-premise not [[IAM]]
![[Pasted image 20230316223154.png|512]]

https://aws.amazon.com/directoryservice/