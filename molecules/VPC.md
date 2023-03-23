# Virtual Private Cloud (VPC)

A [VPC](https://docs.aws.amazon.com/vpc/latest/userguide/configure-your-vpc.html) is a virtual network that closely resembles a traditional network that you'd operate in your own data center. After you create a VPC, you can add subnets.

1. [Virtual Private Cloud (VPC)](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html): Slice of the cloud

* Foundational service that creates a private virtual network to launch resources.
* Spans AZs in a region.
* VPC A and VPC B can be [peered](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html) so they act as one logical VPC.You can create a VPC peering connection between your own VPCs, or with a VPC in another AWS account. The VPCs can be in different Regions (also known as an inter-[Region](Region.md) VPC peering connection).

* The default VPC always exists in every region. But all new VPCs are region specific.

### Subnets

![[Subnet]]
You can add two CIDR ranges to a Subnet. Tied to AZ. Public Subnet - connects to IGW.

[[NACL]] protects subnets.

[[Security Groups]] protect EC2.

### IP Addressing

![[IP Address]]

### Route Tables

![[RouteTable]]

### Gateways

![[GW | Gateway]] and endpoints

- See [[VPC Connectivity]] for more options on interconnecting VPN.

### VPC Endpoints

**Traffic Mirroring**

[Copy network traffic](https://docs.aws.amazon.com/vpc/latest/mirroring/) from network interfaces and send it to security and monitoring appliances for deep packet inspection.

**Transit [[GW]]**

Use a [transit gateway](https://docs.aws.amazon.com/vpc/latest/userguide/extend-tgw.html), which acts as a central hub, to route traffic between your VPCs, VPN connections, and AWS Direct Connect connections.

**VPC Flow Logs**

A [flow log](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html) captures information about the IP traffic going to and from network interfaces in your VPC.

**[[VPN]] connections**

Connect your VPCs to your on-premises networks using [AWS Virtual Private Network (AWS VPN)](https://docs.aws.amazon.com/vpc/latest/userguide/vpn-connections.html).

[[ENI]] is a logical component of a VPC that represents a virtual network card.

[[ELB]] on AWS is at the edge of the VPC architecture