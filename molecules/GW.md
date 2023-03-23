A [gateway](https://docs.aws.amazon.com/vpc/latest/userguide/extend-intro.html) connects your VPC to another network. For example, use an [internet gateway](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) to connect your VPC to the internet. Use a [VPC endpoint](https://docs.aws.amazon.com/vpc/latest/privatelink/privatelink-access-aws-services.html) to connect to AWS services privately, without the use of an internet gateway or NAT device.

### Gateways on AWS
-   **Customer gateway**: An AWS resource which provides information to AWS about your customer gateway device.
    
-   **Customer gateway device**: A physical device or software application on your side of the Site-to-Site VPN connection.
    
-   **Target gateway**: A generic term for the [[VPN]] endpoint on the Amazon side of the Site-to-Site VPN connection.
    
-   **Virtual private gateway**: A virtual private gateway is the VPN endpoint on the Amazon side of your [[Site-to-Site VPN]] connection that can be attached to a single [[VPC]].
    
-   **Transit gateway**: A transit hub that can be used to interconnect multiple VPCs and on-premises networks, and as a VPN endpoint for the Amazon side of the Site-to-Site VPN connection.
#### Internet Gateway
![[IGW]]

#### NAT Gateway
![[NATGW]]