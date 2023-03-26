## Summary
Build loosely coupled event driven architecture at scale with Event Bridge. #AWSService 

## EventBridge Details
- Create a custom [event bus](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-event-bus.html) to receive [events](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-events.html) from your applications. 
-  Applications can also send events to the default event bus. When you create an event bus, you can attach a [resource-based policy](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-use-resource-based.html) to grant permissions to other accounts.
- Event Bridge can have a rule to run an [[ECS]] task. (requires ECS Task Role)
>**EventBridge Event Bus versus Event Bridge Pipe**
> 	EventBridge event buses are well suited for many-to-many routing of events between event-driven services.
> 	 [EventBridge Pipes](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-pipes.html) is intended for point-to-point integrations between these [sources](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-pipes-event-source.html) and [targets](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-pipes-event-target.html), with support for advanced transformations and [enrichment](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-pipes.html#pipes-enrichment).
 #### Resource based and identity based policies.
 For Kinesis streams, EventBridge uses [identity-based](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-use-identity-based.html) policies.
 For Lambda, Amazon SNS, Amazon SQS, and Amazon CloudWatch Logs resources, EventBridge uses resource-based policies. [More](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-use-resource-based.html)

## References

1. [AWS Event Bridge](https://aws.amazon.com/eventbridge/) 
2. https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-create-event-bus.html