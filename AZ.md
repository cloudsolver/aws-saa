## [AZ](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)

* An Availability Zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity in an AWS Region.
* Usually 3, maximum is 6.
	* Each AZ is one or more discrete data centers with redundant power, networking and connectivity.
	* They're separate from each other, so that they're isolate from disaster.
	  They're connected with high bandwidth.
* AZs give customers the ability to operate production applications and databases that are more highly available, fault tolerant, and scalable than would be possible from a single data center.
* All AZs in an AWS Region are interconnected with high-bandwidth, low-latency networking, over fully redundant, dedicated metro fiber providing high-throughput, low-latency networking between AZs.
* All traffic between AZs is encrypted.
* The network performance is sufficient to accomplish synchronous replication between AZs.
* If applications are distrbuted - deploy to multiple AZs with load balancing.