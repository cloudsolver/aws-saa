## Summary
Bucket settings to Block Public Access can be set at the account level, and bucket level which will override any bucket-level policy that allows direct public access. Disable ACLs, use Bucket Policies
## S3 Security Details

1. Disable ACLs.
2. S3 should use Bucket Policies - which is a resource based policy.
3. Review all buckets that have a `*` wildcard on Principal and/or Action.
4. Use IAM Roles for AWS Services.
5. Ensure least privilege.
6. Encrypt Data at Rest with SSE or CSE.
7. WORM with S3 Locks.
8. Cross-Region Replication and Versioning.
9. Identity and audit all S3 buckets.
10. Enable AWS S3 access logging. 
11. Enable [[CloudTrail]] , AWS [[Config]], [[Macie]] and use [S3 Storage Lens](S3.md#S3%20Storage%20Lens) 
### S3 Bucket Policies
The policy below has  a Version, and Statement (array). Each Statement has a statement id, effect, principal, action.
```
{
"Version":"2012-10-17",
"Statement":[
{
	"Sid":"PublicReadGetObject",
	"Effect":"Allow",
	"Principal":"*",
	"Action":"s3:GetObject",
	"Resource":"arn:aws:s3:::spectrumvending.com/*"
	
}
]
}
```
## References

1. [S3 Security Best Practices](https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html)