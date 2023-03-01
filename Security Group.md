Is a stateful firewall for [[EC2]] instances. Inbound and outbound traffic is paired at the port/IP level. 
Many instances can share a security group.
SG is locked down to a region/[[VPC]] combination.
#bestpractice maintain one separate security group for [[SSH]] access.
If application is not accessible, it is a security group issue. If your application returns an error such as 'connection refused' it's actually an application error or it's not launched.
All inbound traffic is blocked by default. 
All outbound traffic is authorized by default.
Security Groups can authorize other security groups  without thinking about IP. 

Priviledged [[Ports]] are required to be memorized.