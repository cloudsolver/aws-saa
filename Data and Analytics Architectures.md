AWS offers [[Athena]], [[Redshift]], [[OpenSearch]], [[Kinesis#Kinesis Data Stream]], [[Kinesis#Kinesis Data Firehose]],  [[EMR]], [[QuickSight]], [[Glue]], [[Lake Formation]] and [[Flink]].


| Technology         | Purpose                    | Architecture                                                   |
| ------------------ | -------------------------- | -------------------------------------------------------------- |
| [[Redshift]]       | Data warehouse             | Handles exabyte-scale data. Indexes for high performance.      |
| [[Glue]]           | ETL                        | Serverless. Out-of-the-box integration for Athena              |
| [[Lake Formation]] | Data Lake                  | Serverless. Fine-grained permissions.                          |
| [[QuickSight]]     | BI Analytics Visualization | Users and Role are separately managed from [[IAM]].            |
| [[Athena]]         | SQL for S3                 | Serverless. Federated query. Glue. Cost optimization - no etl. |
| [[Data Pipeline]]  | Move Data                  | Supports [[Hybrid Cloud Architecture]]                                                               |





1. [Data Pipeline](https://aws.amazon.com/datapipeline/) :

* Helps you move data between compute and storage services running either AWS or on-premises

* Move data based on conditions, intervals and sends notifactions

* Move from S3 to Redshift.

## Big Data and Search

1. [EMR](https://aws.amazon.com/emr/) Map Reduce

* Process large amounts of data via map reduce.

* Analyze data using Hadoop and Apache Spark.

* Usecase: Perform big data analytics, build scalable data piplelines, process real-time data streams, accelerate data science and ML adoption.

2. [OpenSearch](https://aws.amazon.com/opensearch-service/) Interactive Log Analytics

* Search petabytes of unstructured data.

*

* Open source Elastic Search, Open Search Dashboard and Kibana.