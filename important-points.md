#### AWS services which encrypts data at rest by default:
* Storage gateway
* Glacier

#### EBS volumes to handle data warehouse workload where full table scans will be executed frequently:
* Throughput Optimized HDD (st1)

#### A solutions Architect is designing a new workload where an AWS Lambda function will access an Amazon DynamoDB table.What is the MOST secure means of granting the Lambda function access to the DynamoDB table
* Create an identity and access management (IAM) role allowing access from AWS Lambda and assign the role to the DynamoDB table.

#### When you automate snapshot management, it helps you to:

* Protect valuable data by enforcing a regular backup schedule.

* Retain backups as required by auditors or internal compliance.

* Reduce storage costs by deleting outdated backups.

When combined with the monitoring features of Amazon CloudWatch Events and AWS CloudTrail, Amazon Data Lifecycle Manager provides a complete backup solution for EBS volumes at no additional cost.

[Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/snapshot-lifecycle.html)

#### Shared Responsibility Model

<img src="/awssharedrespmodel.jpg">

#### To ensure that the incoming traffic to the host instances of an ECS cluster is from an ALB only:
* Modify the security group used by the EC2 cluster to allow incoming traffic from the security group used by the ALB only.

#### [Controlling which Auto Scaling instances terminate during scale in](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-instance-termination.html)

#### If data stored in S3 is to be analysed:
* Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL. Athena is serverless, so there is no infrastructure to manage, and you pay only for the queries that you run

* Amazon RedShift is used for analytics but cannot analyze data in S3

* AWS Glue is a fully managed extract, transform, and load (ETL) service that makes it easy for customers to prepare and load their data for analytics. It is not used for analyzing data in S3

* AWS Data Pipeline is a web service that helps you reliably process and move data between different AWS compute and storage services, as well as on-premises data sources, at specified intervals

#### 
* 

#### 
* 

#### 
* 
