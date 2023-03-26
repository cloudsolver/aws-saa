### VPC to VPC

#### Peering connections

- AWS-provided network connectivity between two VPCs.
- Use a [VPC peering connection](https://docs.aws.amazon.com/vpc/latest/peering/) to route traffic between the resources in two VPCs.

#### AWS Transit Gateway
[[TGW]] - AWS-provided regional router connectivity for VPCs

#### Software Site-to-Site VPN

- Software appliance- based VPN connections between VPCs

#### Software Site VPN to AWS Managed VPN
- Software appliance to VPN connection between VPCs
- AWS managed high availability VPC VPN connection
- Supports a wide array of VPN vendors and products managed by you
- Supports static routes and dynamic BGP peering and routing

#### AWS Managed VPN
- VPC-to-VPC routing managed by you over IPsec VPN connections using your equipment

#### AWS Private Link
- AWS-provided network connectivity between two VPCs using interface endpoints.

More information on [AWS Whitepaper](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/amazon-vpc-to-amazon-vpc-connectivity-options.html)