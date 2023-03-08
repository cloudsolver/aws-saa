## Summary
S3 can host static websites directly in buckets.
## S3 Website Details
* URL pattern:  `http://bucketname.s3-website.awsregion.amazonaws.com`
	* `s3-website-awsregion` can be hyphenated in certain regions.
	* `http://spectrumvending.com.s3-website-us-east-1.amazonaws.com` is hosted on S3.
* `403 Forbidden` - make sure policy allows pubic reads.
## References

1. [S3 Web Hosting](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)
2. 