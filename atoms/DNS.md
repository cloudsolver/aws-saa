## Summary
Domain Name System (DNS) is a hierarchical naming structure that translates host names to IP Addresses.


## DNS Details
URL resolution happens right to left.
https://www.resume.rohitsood.com 
Right to left: com is the tld.
rohitsood.com is the sld (second leve)

### Browser access example.com
1. Browser connects to a local DNS server
	1. This is managed or assigned by ISP
2. Root Name Server
3. TLD Name Server
4. SLD Name Server
5. Browser gets IP Address
6. Sends request to IP Address
### Domain Registrar
### DNS Records
* Each record contains domain / sub-domain name.
- Record Type
	- A => IPv4, 
	- AAAA=>IPv6,
	- CNAME=>name mapped to another name that has an A record - cannot be an apex, [RFC 1034](https://tools.ietf.org/html/rfc1034) states that the zone apex must be an A Record, and not a CNAME record. You can create a CNAME for `www.rohitsood.com` but not `rohitsood.com`.
	- NS
- Value
- Routing Policy
- TTL - time to live for cache
### Zone File
### Name Server
- Authoritative or Non-Authoritative
### Top Level Domain (TLD)
- com is the top level domain
### Second Level Domain (SLD)
- rohitsood.com
- resume is sub-domain

### URI, URC, URL and URN

All URLs, URCs and URNs are types of URIs.

![Venn| 300](https://i.stack.imgur.com/FbaKm.png)
## References

1. https://stackoverflow.com/questions/176264/what-is-the-difference-between-a-uri-a-url-and-a-urn
1. https://aws.amazon.com/blogs/networking-and-content-delivery/solving-dns-zone-apex-challenges-with-third-party-dns-providers-using-aws/