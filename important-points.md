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

#### 
* 

#### 
* 

#### 
* 
