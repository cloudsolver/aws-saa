## Summary

Read scalability is achieved by asynchronously pushing data to up to five read replicas within an AZ, across AZs or Cross Region. 

## Introduction

Engines have native asynchronous replication features that are used to keep the read replicas up-to-date when changes are made to the primary. Enhanced performance, increased availability and secure.

![|250](https://d1.awsstatic.com/asset-repository/read-replicas-scaling-disaster-recovery.3b8da7093daeb1e87426225caf49e32efe7ae01a.png)

- Maximum 5 Read Replicas for Oracle and Microsoft. Max 15 for MySQL, Maria and PostgreSQL.
- Applications must be updated to a read-replica connection string.
- Replication is asynchronous.
- Replicas can be promoted to their own DB.
- Encryption at rest with [[KMS]] can be enabled.

## References

- https://aws.amazon.com/rds/features/read-replicas/
