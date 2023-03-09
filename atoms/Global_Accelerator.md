## Summary
It directs global traffic via closest edge locations and Anycast IP through internal Amazon network to improve performance and stability. 
## Global_Accelerator Details
- Makes your application go global. #wellarchitected 
- Enables disaster recovery and failover to another region's ALB. #resilient  
- Improve performance and stability. Application is deployed in one region, however there are users all over the world. How can global users work on the app without going through the Internet across so many hops? To minimize latency.
Two Anycast IP Addresses are created and a DNS entry are provided with the creation of the Global Accelerator. Leverage AWS global network from the edge location to the public ALB via AWS private network. 

**Unicast**: one server one IP.
**Anycast** IP: all servers hold the same IP address and the client is routed to the nearest one.
Supported: ElasticIP, EC2, ALB, NLB.
#### Security
- Only 2 external IP need to be whitelisted.
- DDoS protection from AWS [[Shield]]
#### Standard Accelerator

#### Customer Routing
## References

1. [Types of Global Accelerators](https://docs.aws.amazon.com/global-accelerator/latest/dg/introduction-accelerator-types.html)