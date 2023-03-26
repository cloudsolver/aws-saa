# Virtual Private Cloud (VPC)

A VPC is a virtual network that closely resembles a traditional network that you'd operate in your own data center. After you create a VPC, you can add subnets. [more on VPC overview](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)

* Foundational service that creates a private virtual network to launch resources.
* Spans [[AZ|Availability Zones]] in a region. [more on VPC config](https://docs.aws.amazon.com/vpc/latest/userguide/configure-your-vpc.html)
* VPC A and VPC B can be peered so they act as one logical VPC.You can create a VPC peering connection between your own VPCs, or with a VPC in another AWS account. The VPCs can be in different Regions (also known as an inter-[Region](Region.md) VPC peering connection). More on [peering](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html) 
* The default VPC always exists in every region in the account and has Internet connectivity. But all new VPCs are region specific. _Limit to 5 per region (soft)_


### Subnets

You can add two CIDR ranges to a [[Subnet]]. Tied to AZ. Public Subnet - connects to IGW.

[[NACL]] protects subnets. #secure 

[[Security Groups]] protect EC2. #secure

### IP Addressing

![[IP Address]]
[[ENI]] is a logical component of a VPC that represents a virtual network card.

### Route Tables
Routing for subnets and gateways.
[[RouteTable]]

### Gateways

[[GW | Gateway]] and endpoints.

- See [[VPC Connectivity]] for more options on interconnecting VPN.


### VPC Traffic Mirroring

[Copy network traffic](https://docs.aws.amazon.com/vpc/latest/mirroring/) from network interfaces and send it to security and monitoring appliances for deep packet inspection.

### Transit [[GW]]

Use a [transit gateway](https://docs.aws.amazon.com/vpc/latest/userguide/extend-tgw.html), which acts as a central hub, to route traffic between your VPCs, VPN connections, and AWS [[DX]] connections.

### VPC Flow Logs

A [flow log](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html) captures information about the IP traffic going to and from network interfaces in your VPC.
VPC Flow Logs is a VPC feature that enables you to capture information about the IP traffic going to and from network interfaces in your VPC.

#### AWS 

Connect your VPCs to your on-premises networks using [AWS Virtual Private Network (AWS VPN)](https://docs.aws.amazon.com/vpc/latest/userguide/vpn-connections.html).


[[VPN]] is a Virtual Private Network.
[[ELB]] on AWS is at the edge of the VPC architecture.

### Quiz

#Q You have attached an Internet Gateway to your VPC, but your EC2 instances still don't have access to the internet. What is **NOT** a possible issue?
> a. Route Table
> b. SG ingress rules
> c. NACL egress rules
> d. EC2 only has a private IP
> e. NACL ingress rules for 1024-65535
> Answer: It is true that an EC2 instance cannot connect to the Internet (via IGW) when it does not have a public IP address. It is also true that without a route to the IGW within the subnet that the the EC2 instance is running, it will not be able to reach the internet. Finally, NACL needs to allow egress on 80 and 443 assuming it's the web EC2 wants to reach. Therefore, SG ingress makes no sense at all. Why? If SG egress allows it, then ephemeral ports will automatically open to ingress.  NACL must be permissive

#Q Which of the following VPC resources is highly available but not fault tolerant?
(a) Internet Gateway
(b) NAT Gateway
(c) VPC Gateway
(d) VPC Peering Connection
Answer: IG is fault tolerant, so is VPC Gateway and VPC Peering Connection.