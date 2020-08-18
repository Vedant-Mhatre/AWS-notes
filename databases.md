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
Enabled by default, backup is stored in S3 and you get free storage space equal to the size of db.
During backup you may experience elevated latency

2. Database Snapshots: are done manually. Stored even after you delete RDS instance, unlike automated backups.

Whenver you restore either an automatic backup or manual snapshot, restored version of database will be new RDS instance with a new DNS endpoint.

Encryption at rest is supported for MySQl, Oracle, SQL Server, PostgresSQL, MariaDB and Aurora, it is done using AWS key management service(KMS) service.
Once RDS instance is encrypted automated backups, read replicas and snapshots are also encrypted.

Multi AZ: allows you to have an exact copy of your production database in another AZ. When anything is written in production database, it is automatically synchorized to stand by database.

In event of primary db failure, AWS will automatically failover to the standby so that db operations can resume quickly without administrative intervention.

***
Multi AZ is for disaster recovery only.

It is not primarily used to improve performance.

You need read replicas for improving performance.
***

Read Replicas: allow you to have a read-only copy of your production database. This is achieved by using asynchronous replication from primary RDS instance to the read replica. You use read replicas primarily for very-read heavy database workloads.

You can have multiple EC2 instances writing to one read replica each and have all write to one primary RDS instance.

Must have automatic backups turned on in order to deploy a read replica.

You can have upto 5 read replicas for any db

You can have read replicas of read replicas but be aware of latency

Each read replica will have its own DNS end point

You can have read replicas that have multi AZ

You can create read replicas of multi AZ database

Read replicas acn be promoted to be their own databases. This breaks the replication

You can have read replica in second region

