# Virtual Private Cloud (VPC)

A [VPC](https://docs.aws.amazon.com/vpc/latest/userguide/configure-your-vpc.html) is a virtual network that closely resembles a traditional network that you'd operate in your own data center. After you create a VPC, you can add subnets.

1. [Virtual Private Cloud (VPC)](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html): Slice of the cloud

* Foundational service that creates a private virtual network to launch resources.
* Spans AZs in a region.
* VPC A and VPC B can be [peered](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html) so they act as one logical VPC.You can create a VPC peering connection between your own VPCs, or with a VPC in another AWS account. The VPCs can be in different Regions (also known as an inter-[Region](Region.md) VPC peering connection).

* The default VPC always exists in every region. But all new VPCs are region specific.

**Subnet**

A [subnet](https://docs.aws.amazon.com/vpc/latest/userguide/configure-subnets.html) is a range of IP addresses in your [[VPC]]. A [[Subnet]] must reside in a single [[AZ]]. After you add subnets, you can deploy AWS resources in your [[VPC]].

**IP addressing**

You can assign IPv4 addresses and IPv6 addresses to your VPCs and subnets. You can also bring your public IPv4 and IPv6 GUA addresses to AWS and allocate them to resources in your VPC, such as [EC2](EC2.md) instances, NAT gateways, and Network Load Balancers.

**Routing**

Use [route tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html) to determine where network traffic from your subnet or gateway is directed.

**[[Gateways]] and endpoints**

A [gateway](https://docs.aws.amazon.com/vpc/latest/userguide/extend-intro.html) connects your VPC to another network. For example, use an [internet gateway](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) to connect your VPC to the internet. Use a [VPC endpoint](https://docs.aws.amazon.com/vpc/latest/privatelink/privatelink-access-aws-services.html) to connect to AWS services privately, without the use of an internet gateway or NAT device.

**Peering connections**

Use a [VPC peering connection](https://docs.aws.amazon.com/vpc/latest/peering/) to route traffic between the resources in two VPCs.

**Traffic Mirroring**

[Copy network traffic](https://docs.aws.amazon.com/vpc/latest/mirroring/) from network interfaces and send it to security and monitoring appliances for deep packet inspection.

**Transit [[Gateways]]**

Use a [transit gateway](https://docs.aws.amazon.com/vpc/latest/userguide/extend-tgw.html), which acts as a central hub, to route traffic between your VPCs, VPN connections, and AWS Direct Connect connections.

**VPC Flow Logs**

A [flow log](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html) captures information about the IP traffic going to and from network interfaces in your VPC.

**[[VPN]] connections**

Connect your VPCs to your on-premises networks using [AWS Virtual Private Network (AWS VPN)](https://docs.aws.amazon.com/vpc/latest/userguide/vpn-connections.html).

[[ENI]] is a logical component of a VPC that represents a virtual network card.

[[ELB]] on AWS is at the edge of the VPC architecture