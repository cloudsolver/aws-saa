## Summary
DR is the process of preparing for and recovering from a disaster. A resilient architecture will plan for business continuity via disaster recovery plan. #resilient 
## Disaster Recovery Details
Disaster Recovery can use multiple methods and there are various types.
 #### Backup
	Store data off site. 
	IT infrastructure is not backed up.
	Support point in time recovery.
- Cold Site
		- Business operations can continue in rarely use facility but this must be complemented with another data and infrastructure backup and restoration.
	- Hot Site
		- Up-to-date copies of data allows dramatic reduction in down time.
	- DRaaS
		- Disaster or Ransonware attack - the organization's infrastructure is moved to the organizations computer processing to enable business continuity.
	- Backup as a Service
		- Third party is contracted to back up data but not infrastructure.
	- Virtualization
		- Offsite virtual machines with synchronized data.
	- Data-center disaster recovery
		- Physical protections to recover faster e.g. fire suppression, backup power etc.
	- Point-in-time copies
		- Entire database is copied.
	- Instant recovery
		- Snapshot an entire VM without database copies.
### Measures


![DR|500](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/04/02/Figure-1.png)

[[RPO]] is the recovery point objective.
[[RTO]] is the recovery time objective.

### References

1. https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html?did=wp_card&trk=wp_card
2. https://aws.amazon.com/blogs/architecture/disaster-recovery-dr-architecture-on-aws-part-i-strategies-for-recovery-in-the-cloud/
3. https://docs.aws.amazon.com/pdfs/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.pdf#disaster-recovery-workloads-on-aws
4. https://www.vmware.com/topics/glossary/content/disaster-recovery.html