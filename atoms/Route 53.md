## Summary
Highly scalable and highly available [[DNS]] service that supports various record types, routing policies and domain registration. #awsservice A hosted zone is analogous to a traditional DNS zone file, and Alias records are an extension to DNS that is AWS specific.
## Route 53 Details

### Record Type
- A => IPv4, supports multiple IP addresses. #resilient 
	- Alias (AWS Extension) Records are used to point a hostname to an AWS Resource such as CloudFront distribution (rohitsood.com => d2ysinytc0i3i0.cloudfront.net.). This is how you point your zone apex to an Amazon Resource such as ELB. There is no additional charge. #cost-optimize 
	- You cannot use an Alias for an EC2 DNS name or S3 Buckets! You can however use it for an ELB, VPC Interface Endpoints, S3 Websites, Elastic Beanstalk infrastructure, .
	- AWS Resources expose an AWS Hostname that can be used with an A record (alias) - free and has health check.
- AAAA=>IPv6
		- Alias - same as A record Alias. Automatically recognizes changes in resource IP address. It can be used for top node of a DNS Namespace i.e Zone Apex.
- CNAME=>name mapped to another name that has an A record - cannot be an apex, [RFC 1034](https://tools.ietf.org/html/rfc1034) states that the zone apex must be an A Record, and not a CNAME record. You can create a CNAME for `www.rohitsood.com` but not `rohitsood.com`.
	- No Apex records allowed under CNAME.
- NS - name server records
	- Does not support wild-cards.
- Value
- Routing Policy
- TTL - time to live for cache. DNS responds with IP address the TTL. 
- If you set a high TTL such as 24hrs - there will less traffic.

### Route 53 Routing Policy
Route 53 supports the following Routing Policies:
#### Simple Routing Policy
- Single resource that typically serves a single function.
- Only option is to have multiple IPs in the same record because multiple records with the same name are not possible. Unless you're pointing to an alias record only one can be created.
- R53 will return the records to the resolver in random order if IP addresses are used.
#### Weighted Routing Policy
- Routes to multiple resources based on specified weights (0-255). 
- R53 will respond with an IP address based on the weights.
#### Failover Routing Policy
- Routes to primary resource, then fails over to secondary resource if health deteriorates. High availability with an active-passive architecture. #resilient
- Create a Failover group within the records with the same name. Use a primary and secondary resources for the failover. "You must create one primary and one secondary failover record." 
#### Latency Based Routing Policy
 - By using `latency records` it routes to primary resources, then switches to secondary resource if the latency criteria is not met. Typically, useful when multiple regions have hosted the resources.
- Latency based routing selects the path of least latency.
#### Geo-location Routing Policy
- By mapping IP addresses to locations it routes to resources that are based on the region of the request. Based on where users are their requests can be routed.
- You can also use geolocation routing to restrict distribution of content to only the locations in which you have distribution rights. #usecase 
- You can use localization and i18n for users by routing with this policy. #usecase 
#### Multi-Value Answer Routing Policy
- Route 53 returns multiple values for the request at random and based on health. 
- Ability to return multiple health-checkable IP addresses is a way to use DNS to improve availability and load balancing. #resilient #performant 
#### Geo-proximity Routing Policy
- By using Route 53 `traffic flow` it routes to resources closest to the request. Shift requests from one location to another.
### Route 53 Health Checks
HTTP Health Checks are only for public resources. Route 53 checkers are outside the VPC. They can't access private endpoint. You must create a CloudWatch Metric and associate a CloudWatch Alarm and have the Route53 Health Checker use that instead.
1. Endpoint Monitoring
	1. 15 Global Health Checkers (must allow incoming Health Checker IP [address range](https://ip-ranges.amazonaws.com/ip-ranges.json)
	1. Healthy if > 18% is healthy
	1. Search response text first 5120 bytes
2. Calculated Health Checks
		1. Combines the results of multiple health checks into a single health checks
		2. Parent => Child (256) OR, AND, NOT logic

## References

1.  https://aws.amazon.com/route53/
2. https://aws.amazon.com/route53/faqs/
3. https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-edns0.html
4. https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html
5. https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resource-record-sets-values-failover.html
1. https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-latency.html