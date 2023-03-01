 [[EC2]]  Elastic Cloud Compute is a core #awsservice that runs virtual servers within a [[VPC]].
* Bootstrap with EC2 User Data - run once at instance first start.
	* Install updates, software, download comming files etc as sudo.
* Instance Naming Convention: m5.2xlarge m=instance class, 5=generation, 2xlarge=size of instance within class.
* General Purpose: Web-server, application servers, 
* Compute Optimized: Media transcoding, batch processing, high performance web servers, high performance computing (HPC), machine learning, scientific modeling and dedicated gaming server.
* Memory Optimized: High performance, relational and non-relational database, distributed web scale cache stores, In-memory databases optimized for BI, applications performing real-time processing of big unstructure data.
* #tip Use this website to checkout the EC2 Instance types https://instances.vantage.sh/

[[Security Group]] is a firewall for EC2.

You can connect to EC2 via [[EC2 Instance Connect]] or [[SSH]] assuming the [[Security Group]] has been setup.

#bestpractice Do not run `aws configure` into an EC2 instance. [[IAM]] Roles should be used : attach the role to the EC2 instance. Based on the role, you can run aws commands such as `aws iam list-users` from within the EC2 instance.

## EC2 Instance Purchasing Options
* On-Demand Instances
	* Highest cost
* Reserved
	* Reserved Instance: 72% discount. 
		* 1 year or 3 year
		* Instance Type, Region, Tenancy, OS
	* Convertible Reserved Instance
		* Can change the EC2 instance type, instance family, OS, scope and tenancy.
		* Up to 66% discount.
* Savings Plan
	* Get a discount based on long-term usage (up to 72% - same as RIs)
	* Commit to billable usage for 1 or 3 years.
	* Usage beyond the committment defaults to On-Demand price.
	* Flexibility: Instance size within family, OS, and tenancy e.g. default, dedicated, host.
* Spot Instances
	* 90% discount. Region, and AZ prices vary.
	* You will get 2-minute warning via EC2 meta-data before shutdown. 
	* Spot Block - timeframe 1-6 hours of no interruption.
	* Spot request: One-time or Persistent.
	* #usecase: batch, data analysis, image processing, distributed workloads, flexible start and end times.
	* #antipattern Not suitable for critical jobs or databases.
	![[spot-instance-state-diagram.png]]
	* There are two types of spot requests: persistent and one-time. Refer to the state machine.
	* Cancel the spot request first, then cancel the spot instances. This way, new spot instances won't be created.
* Spot Fleets
	* Set of Spot Instnaces and Optional On-Demand Instances.
	* The spot fleet will try to meet the target capacity with price constraints.
	* Can have multiple launch pools, so that the fleet can choose. It will stop launching instances based on price constraints.
* Dedicated Hosts
	* Physical server with EC2 instance capacity.
	* #usecase compliance requirements, server-bound software license e.g. per-socket, per-core or BYOL.
* Dedicated Instances
	* Hardware shares with instances of the same account.
	* No control over instance placement.
* Capacity Reservation
	* Reserver On-Demand instance capacity in a specific AZ for any duration.
	* You always hav access to EC2 capacity when you need it.
	* No time commitment.