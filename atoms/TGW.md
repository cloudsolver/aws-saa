**Transit gateway**:
A transit hub that can be used to interconnect multiple VPCs and on-premises networks, and as a VPN endpoint for the Amazon side of the Site-to-Site VPN connection.
[[VPC Connectivity#Peering connections]] are not transitive. The transit [[GW|gateway]] accomplishes this easily without N*(N-2) peering connections. Simply by adding route propagation to the peering attachments.

![[Transit Gateway Peering.png|512]]
Fig. Transit Gatewa Hub and Spoke Peering Inter-Region VPC Cross Account