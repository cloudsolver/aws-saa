### Summary of KMS
Key management system is an #AWSService that automates encryption key management. #secure 
### KMS Details

- Centrally manage [[encryption]] keys and define policies.
- AWS Encryption SDK library should be used from within applications.
- Validate [[Digital Signatures]] and perform signing operations using asymmetric digital keys.
- Message authenticity and integrity with [[HMAC]] (Hash-based Message Authentication Codes)

> **KMS Monitoring**
> KMS is monitored by [[CloudWatch]] and its usage tracked by [[CloudTrail]]

> **KMS Seamless Integration**
>  KMS seamlessly integrates with [[EBS]], [[S3]], [[RDS]], [[SSM]]

#### Types of KMS Keys

|                    | AWS Managed           | Customer Managed |
| ------------------ | --------------------- | ---------------- |
| AWS Generated      | AWS Owned and Managed (annual rotation) | Created in KMS, annual rotation must be enabled.   |
| Customer Generated | Imported to AWS (symmetric only)               | Manual rotation only                |

### Cross-Region
Keys created by the service AWS KMS are never transmitted outside of the AWS Region in which they were created. They can be used in only the Region in which they were created.

Your plaintext keys are never written to disk and only ever used in volatile memory of the HSMs for the time needed to perform your requested cryptographic operation. This is true regardless of whether you request AWS KMS to create keys on your behalf, import them into the service, or create them in an AWS [[CloudHSM]] cluster using the custom key store feature. Keys created by the service AWS KMS are never transmitted outside of the AWS Region in which they were created. They can be used in only the Region in which they were created.

An [[EBS]] snapshot in Region A with Key 1 needs to be re-encrypted into Region B with Key 2. Key 1 cannot be used in Region B.


---
> **References for KMS**
> 1. https://aws.amazon.com/kms/
> 2. https://aws.amazon.com/kms/features/#AWS_Service_Integration
> 
 
*Created on 2023-03-19 15:26*
