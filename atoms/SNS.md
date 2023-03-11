### Summary of SNS
Simple Notification Service is a fully managed instantaneous pub/sub service for Application to Application and Application to Person messaging. It supports SMS and MobilePush. #awsservice 
### SNS Details
- 100,000 topics, 12,500,000 subscribers per topic.
- Many Amazon Services connect to SNS e.g AWS Budgets, CloudFormation, ASG, S3, Dynamo, DMS etc.
- SNS is both highly reliable and scalable, it provides significant advantages to developers who build applications that rely on real-time events.
- SNS can send `Email-JSON` for applications to read and process emails. Humans get text-based emails only.
- SNS Mobile Push lets you use SNS to deliver push notifications to Apple, Google, FireOS and Windows devices as well as Android.

#### SNS Security
SNS Access Policies (similar to S3 bucket policies)
- Useful for cross-account access to SNS topics
- Useful for allowing other services ( S3…) to write to an SNS topic
- SNS supports [CloudTrail](CloudTrail) to get a history of SNS API calls made for security analysis.


### Solution Architecture

SNS Fan-Out to SQS and Lambda.
![](Pasted%20image%2020230310221856.png)

SNS FIFO Fan-Out to SQS FIFO
![](Pasted%20image%2020230310222059.png)
#### References for SNS
1. https://aws.amazon.com/sns/
2. https://aws.amazon.com/sns/faqs/
3. https://docs.aws.amazon.com/sns/latest/dg/sns-mobile-application-as-subscriber.html
###### Timestamp
---
Created on 2023-03-10 22:11