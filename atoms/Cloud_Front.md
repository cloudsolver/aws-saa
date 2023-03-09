## Summary
CloudFront is a Content Distribution Service offered by AWS. #awsservice 
## Cloud_Front Details
As soon as the first byte arrives from the origin, CloudFront begins to forward the object to the user. CloudFront also adds the object to the cache for the next time someone requests it. While this service is useful for content distribution however for UDP, and non-HTTP acceleration such IoT this won't work. Instead, we must use [Global_Accelerator](Global_Accelerator.md) if business has more advanced use-cases such as requiring whitelisting IP addresses.

![Architecture|550](https://docs.aws.amazon.com/images/AmazonCloudFront/latest/DeveloperGuide/images/how-you-configure-cf.png)

Regional Caches are large than POPs and can hold less popular objects. This saves a trip to the origin servers and keeps objects cached closest to the customer.

- You can enable geo restrictions in CloudFront. #secure 
- You can choose **Price Class 100**, viewers in India might experience higher latency than if you choose **Price Class 200**. #cost-optimized 
- Lambda@Edge with CloudFront enables a variety of ways to customize the content that CloudFront delivers. #usecase 
- Accelerate static site delivery, VOD, field-level encryption are some of the usecases.

## References

1. [CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html)