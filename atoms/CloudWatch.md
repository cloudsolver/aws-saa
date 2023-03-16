### Summary of CloudWatch
System-wide visibility into resource utilization, application performance, and operational health.
#AWSService 
### CloudWatch Details
- basically a metrics repository. AWS services puts metrics in cloudwatch, custom metrics can be put in cloudwatch
![[Pasted image 20230315221719.png|512]]

| Concept     | Description                                                                                                                  |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Namespace   | A _namespace_ is a container for CloudWatch metrics.                                                                         |
| Metric      | A metric represents a time-ordered set of data points that are published to CloudWatch.                                      |
| Timestamp   | Each metric data point must be associated with a time stamp in UTC - Coordinated Universal Time                              |
| Dimension   | A _dimension_ is a name/value pair that is part of the identity of a metric. You can assign up to 30 dimensions to a metric. |
| Resolution  | Granularity of metric Standard = 1 min and High = 1 sec                                                                      |
| Statistics  | _Statistics_ are metric data aggregations over specified periods of time.                                                    |
| Unit        | Each statistic has a unit of measure. Example units include `Bytes`, `Seconds`, `Count`, and `Percent`.                      |
| Period      | A _period_ is the length of time associated with a specific Amazon CloudWatch statistic.                                     |
| Aggregation | Aggregates statistics according to the period length that you specify e.g. Web hit latency aggregation every 60 seconds      |
| Percentile  | Percentiles are often used to isolate anomalies.                                                                             |
| Alarm       | You can use an _alarm_ to automatically initiate actions on your behalf. An alarm watches a single metric over a specified time period, and performs one or more specified actions, based on the value of the metric relative to a threshold over time                                                                                                                             |
#### References for CloudWatch
1.  https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch-Unified-Cross-Account.html
2. https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_concepts.html
###### Timestamp
---
Created on 2023-03-15 22:16