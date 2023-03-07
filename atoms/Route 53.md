## Summary
Highly scalable and highly available DNS service that supports various record types, routing policies and domain registration. #awsservice A hosted zone is analogous to a traditional DNS zone file, and Alias records are an extension to DNS that is AWS specific.
## Route 53 Details

### Record Type
- A => IPv4, supports multiple IP addresses. #reliable 
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

### Routing Policy
Route 53 supports the following Routing Policies
- Simple
	- Typoi
- Weighted
- Failover
- Latency Based
- Geo-location
- Multi-Value Answer
- Geo-proximity
## References
1.  https://aws.amazon.com/route53/
2. https://aws.amazon.com/route53/faqs/