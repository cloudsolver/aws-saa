## Summary
Domain Name System (DNS) is a hierarchical naming structure that translates host names to IP Addresses.


## DNS Details
URL resolution happens right to left.
https://www.resume.rohitsood.com 
Right to left: com is the tld.
rohitsood.com is the sld (second leve)

## Browser access example.com
_This is what happens when you want to visit a website_
1. Browser connects to a local DNS server
	1. This is managed or assigned by ISP
2. Root Name Server
3. TLD Name Server
4. SLD Name Server
5. Browser gets IP Address
6. Sends request to IP Address
## Domain Registrar
- Registers Second Level Domain
### DNS Records
* Each record contains domain / sub-domain name.
[Route 53](Route%2053.md)
### Zone File
### Hosted Zones
- Container for records that define how to route traffic to a domain and sub-domains.
- *Public Hosted Zones* contain records for public domain names.
- _Private Hosted Zone_ contains records for private domain names (e.g. intranet names). $0.50 per month.
- 
### Name Server
- Authoritative or Non-Authoritative
- `dig` and `nslookup` can provide information on the domain name to IP mapping.
#### Top Level Domain (TLD)
- com is the top level domain
#### Second Level Domain (SLD)
- rohitsood.com
- resume is sub-domain
#### URI, URC, URL and URN

All URLs, URCs and URNs are types of URIs.

![Venn| 300](https://i.stack.imgur.com/FbaKm.png)
## References

1. https://stackoverflow.com/questions/176264/what-is-the-difference-between-a-uri-a-url-and-a-urn
1. https://aws.amazon.com/blogs/networking-and-content-delivery/solving-dns-zone-apex-challenges-with-third-party-dns-providers-using-aws/
