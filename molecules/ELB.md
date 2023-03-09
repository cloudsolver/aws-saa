Elastic Load Balancers is an #awsservice that can be set up externally as well as internally.
## CLB
Classic Load Balancer (deprecated)
- CLB : HTTP, HTTPS, TCP, SSL
#### ALB
![Application Load Balancer diagram|250](https://s3.us-east-1.amazonaws.com/elb-polaris-cdk-assets-us-east-1-prod/2023-02-21T01-06-41_f711e1f2085536cdd2e5cf3814c3b7f9a49425fa46543744dace8418e82c80dc/Static/ALBdiagram.svg)
Application Load Balancer

- ALB: [Layer 7](OSI.md#Layer%207): HTTP, HTTPS, WebSocket
- Fixed hostname e.g. xyz.region.elb.amazonaws.com
	- EC2 don't see IP of the client - ALB injects a header `X-Forwareded-For` along with `X-Forwarded-Port` and `X-Forewarded-Proto`
- Routing Tables to different target groups based on:
	- path in URL
	- hostname in URL
	- query strings
	- headers
- #usecase microservices, container-based applications. Port mapping features are useful.
- Target Groups
	- EC2 Instances (can be managed by an ASG) - HTTP
	- EC2 tasks (managed by ECS) - HTTP
	- Lambda functions - HTTP request is translated into JSON event.
	- IP address - must be private IPs.
	- ALB can route to multiple target groups.
	- Health checks at the Target Group level.

A listener is a process that checks for connection requests using the port and protocol you configure. The rules that you define for a listener determine how the load balancer routes requests to its registered targets.

#Q An application is deployed with an Application Load Balancer and an Auto Scaling Group. Currently, you manually scale the ASG and you would like to define a Scaling Policy that will ensure the average number of connections to your EC2 instances is around 1000. Which Scaling Policy should you use?
(a) Simple Scaling Policy
(b) Step Scaling Policy
(c) Target Tracking Policy
(d) Scheduled Scaling Policy
Answer: Target Scaling Policy.
## NLB
Network Load Balancer operates at [Layer 4](OSI.md#Layer%204).
![Network Load Balancer diagram|250](https://s3.us-east-1.amazonaws.com/elb-polaris-cdk-assets-us-east-1-prod/2023-02-21T01-06-41_f711e1f2085536cdd2e5cf3814c3b7f9a49425fa46543744dace8418e82c80dc/Static/NLBdiagram.svg)
- Network: TCP, TLS (Secure TCP), UDP.
- Low latency ~100ms vs ~400ms for [ALB](ELB.md#ALB).
- High throughput with millions of requests per second. 
- Use it for extremely high performance.
- One static IP per AZ, and supports assigning Elastic IP
	- #usecase whitelisting specific IP
- Designs
	- NLB can front a TG consisting of an ALB.
	- NLB can front a TG consisting of an on-prem IP and a private IP.
	- NLB can front a TG consisting of EC2 instances.
- Health Check: Supports TCP, HTTP/S protocols.
- NLB has an IPv address per Subnet in the AZ it is deployed to. So if you deploy to 3 AZs there will be 3 IP addresses.

## GWLB
Gateway Load Balancer
- Gateway: operates at [Layer 3](OSI.md#Layer%203): [IP](TCP-IP.md#IP%20Features) Protocol.
- 2 Functions: 
	- Transparent Network Gateway: Single entry/exit for all traffic.
	- Load Balancer: distributes traffic to virtual appliances.
	 ![Gateway Load Balancer| 200](gwlb.png)
- #usecase Deep packet inspection, firewalls, intrusion detection and prevention systems, deep packet inspection systems, payload manipulation.
- It maintains stickiness of flows to a specific target appliance using 5-tuple (for TCP/UDP flows) or 3-tuple (for non-TCP/UDP flows) by using the [[GENEVE]] protocol on port 6081.
- Cross-zone load balancing distributes traffic across registered targets in all enabled AZs.
- GWLB supports assymetric flow only when the load balancer process the initial flow packet and the response flow packet is NOT routed through the load balancer.
## Session Affinity
- Implement same client is always directed to the same instance behind a load balancer.
- Possible via CLB and ALB via `cookie` that has an expiration date.
### Application Based Cookies
- Custom Cookie : don't use reserved cookie names e.g. `AWSALBTG`
- Application Cookie `AWSALBAPP` 
### Duration Based Cookies
- Load Balancer Generate `AWSALB` or `AWSELB` (Classic)
You can configure this in the Target Group settings.

## Cross-Zone Load Balancing
- With Cross-Zone Load Balancing enabled - each EC2 instance will get same load.
- Without Cross-Zone Load Balancing each AZ gets equal load regardless of EC2 capacity.
- ALB: Enabled by default. No charge.
- CLB: Disabled by default. No charge for enabling.
- NLB and GWLB: Disabled by default. Charges for enabling inter-AZ traffic.

## SSL and TLS  

HTTPS listener 
	You must specify a default certificate. 
	You can add an optional list of certs to support multiple domains.
	Clients can use [[SNI]] (Server Name Indication) to specify the hostname 
Does not work with CLB. Only works with ALB, NLB and CloudFront.
ALB v2 and NLB v2 supports multiple listeners with multiple SSL certificates and uses SNI.
CLB v1 supports only 1 SSL certificate.

## Connection Draining
Time to complete 'in-flight requests' while the instance is de-registering or unhealthy. Stops sending new request to the EC2 instance which is de-registering. During this time new connections to ELB are directed to healthy instances.
Default: 300 seconds. Set to lower values for shorter requests.
## General Notes

- Load Balancer security group should allow users to connect from anywhere via HTTP/S however the EC2 behind it should only allow traffic coming from the load balancer. How? By linking the security group of the EC2 to the load balancer security group as *source* rather than a CIDR.
- #Q For compliance purposes you would like a fixed static IP address to your end-users so they can write firewall rules that will be stable and approved by regulator. What type of ELB would you choose?
	- ALB with an Elastic IP attached to it?
	- NLB?
	- CLB?
	- Answer is NLB. An Elastic IP cannot be attached to an ALB. However, an NLB gets a public IP address on each AZ.