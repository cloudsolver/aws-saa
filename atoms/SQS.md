### Summary of SQS
Exchange messages via at-least-once delivery, best-effort ordering, low-latency, small size, [[FIFO]] messages between distributed applications that employs a polling method. #awsservice 
### SQS Details
- At-least-once delivery and best-effort ordering.
- `SendMessageAPI` to send to SQS. Default message retention period 4 days. Maximum retention is 14 days.
- Low Latency < 10ms, Limitation of 256 KB message size.
- Consumer may receive up to 10 messages at a time. `ReceiveMessage` will get the same message again unless `DeleteMessage` is invoked. 
- If `MessageVisibility` timeout of 30 seconds expires, SQS Queue will deliver a different message to different consumer.
- Long Polling is controlled by RVPNeceive message wait time - between 0 and 20 seconds. It reduces the number of API calls and costs, but it does increase the latency.
- FIFO - exactly once processing (delivered once and remains available until processed by consumer). Q name must end with `.fifo` . Max 300 msg/second and 3K msgs/second with batching. Max 20K in-flight messages at a time *no errors reported if quota breached - must monitor and alert* `ApproximateNumberOfMessagesNotVisible` is a available CloudWatch metric.
![Visibility|500](https://docs.aws.amazon.com/images/AWSSimpleQueueService/latest/SQSDeveloperGuide/images/sqs-visibility-timeout-diagram.png)
#### SQS Security
- Encryption: Supports HTTPS with TLS and encrypts message using SSE with [[KMS]] for storage before it is decrypted and sent to the requesting consumer that is authorized.
- Access: IAM policies regulate access to SQS API. SQS Access Policies (similar to S3) are useful for cross-account access to SQS queues. Useful for allowing other services to write to an SQS Queue.

#### Solution Architectures
#### Scale EC2 Horizontally
Queue Depth measured by CloudWatch triggers an alarm that can request [ASG](ASG.md) to add more EC2 instance #performant and #resilient .
![Solution|400](Pasted%20image%2020230310075710.png) 
The underlying databases should be able to handle the load as well or throttled with limited connections in the pool. Alternatively use a max
#UseCase 

#### Decouple Front End Web from Back End
![](Pasted%20image%2020230310215206.png)
#### References for SQS
1. https://aws.amazon.com/sqs/faqs/
###### Timestamp
---
Created on 2023-03-10 07:47