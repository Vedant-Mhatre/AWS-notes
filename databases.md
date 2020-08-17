RDS has 2 key features:

1. Multi AZ - for disaster recovery

2. Read Replicas - For performance

Data warehousing databases use different type of architecture both from database perspective and infrastructure layer

Redshift: Amazon's data warehouse solution 

ElastiCache is webservice that makes it easy to deploy, operate, and scale an in-memory cache in the cloud. 

2 open source in-memory caching engines:

1. Memcached

2. Redis

RDS (OLTP):
SQL, MySQl, PostgreSQL, Oracle, Aurora, MariaDB

DynamoDB(NOSQL)

RedShift(OLAP)


RDS:

RDS runs on virtual machines

You cannot login to these virtual machines

RDS is not serverless, exception: Aurora Serverless

2 different types of backups for RDS:

1. Automated Backups:recover db to any point in time within a "retention period"(can be between one to 35 days).
Enabled by default, backup is stored in S3 and you get free storage space equal to the size of db

2. Database Snapshots

