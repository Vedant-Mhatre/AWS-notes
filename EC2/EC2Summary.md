EC2 is a web service that provides resizeable compute capacity in the cloud

4 pricing options:

1. On Demand - fixed rate by the hour with no commitment

2. Reserved - Contract terms 1 year to 3 years, more upfront payment, more discount

3. Spot - Bid whatever price you want for instance capacity

4. Dedicated - Physical EC2 server dedicated for your use, mainly used where lot of server-bound licenses exist

#### If spot instance is terminated by EC2, you will not be charged for partial hour of usage. However, if you terminate instance yourself, you will be charged for any hour in which the instance ran.

types:

F - FPGA

I - IOPS

G - Graphics

H - High Disk Throughput

T - Cheap general purpose(T2 Micro, T3 Micro)

D - Density

R - RAM

M - Main choice for general purpose

C - Compute

P - Graphics(think Pics)

X - Xtreme Memory

Z - Extreme memory and Gpu

A - ARM based workloads

U - Bare Metal

Termination protection is turned OFF by default

On EBS backed instance, default action is for root EBS volume to be deleted when the instance is terminated 

EBS root volumes for default AMI can now be encryped when creating instance 

All inbound traffic is blocked by default

All outbound traffic is allowed

You can have multiple security groups attached to EC2 instance

Security groups are stateful - when you open port 80, it will be open for inbound as well as outbound

Network ACL are stateless

#### You cannot block specific IP addresses using security groups, instead use NACL

You can specify allow rules but not deny rules

Snapshots are incremental - only blocks that have changed since your last snapshot move to S3

#### You can create AMIs from both Volumes and Snapshots

You can change EBS volume size on the fly, including changing storage type and size

Volumes will be always be in the same AZ as EC2 instance

#### To move EC2 volume from one AZ to another:
* take snapshot of it, create AMI from it then use that AMI to launch instance in new AZ

#### To move EC2 volume from one region to another:
* take snapshot of it, create AMI and copy AMI to a different region. Then use copied AMI to launch EC2 instance

You can share snapshots only if they are unencrypted, these snapshots can be shared with other AWS accounts or made public

#### If you have an unencrypted root device volume that needs to be encrypted:
Create snapshot of unencrypted root device volume, create copy of snapshot and select encrypt option.
Create AMI from snapshot and use AMI to launch EC2 instance.

## Instance store volumes are called ephemeral storage

* Instance store volumes cannot be stopped. If underlying host fails you will lose your data

* You can reboot it and not lose data

* By default instance store and EBS root volumes are deleted on termination. However, with EBS you can tell AWS to keep root device volume 


#### ENI:
* comes with every EC2 instance
* For basic networking, perhaps you need to separate management network from production network and need to do it at low cost.
* In this scenario use multiple ENIs for each network
    
#### Enhanced Network:
* When you need speeds between 10 GBPS and 100 GBPS. reliable and high throughput

#### Elastic Fabric Adapter:
* When you need to accelerate High Performance Computing (HPC) and machine learning apps or you need to do OS by-pass.


#### In question mentioning HPC or ML and asking adapter choose EFA


CloudWatch is used for monitoring performance
It can monitor most of AWS as well as applications that run on AWS
with EC2 will monitor events every 5 minutes by default

You can create CloudWatch alarms that trigger notifications

#### CloudWatch is all about performance, CloudTrail is all about auditing

What you can do with cloudwatch:
1. Dashboard
2. Alarms - notify when particular thresholds are met
3. Events - respond to state changes in AWS resources
4. Logs - help you aggregate, monitor and store logs

CloudTrail monitors API calls, it can tell who created EC2 instance, etc...

to get metadata:
```
curl http://169.254.169.254/latest/meta-data
```

EFS support NFSv4 protocol
You only pay for storage you use

EBS cannot be shared with multiple EC2 instances, EFS can.
#### Data is stored across multiple AZs within region.


Read after Write consistency

EFS: distributed, highly resilitent storage for linux instances

Amazon FSx for windows: Centralised storage for windows based applications

Amazon FSx for lustre: high speed, high capacity distributed storage. This will be for applications that do HPC, financial modelling etc. 
#### Remember that FSx for Lustre can store data directly on S3


EC2 placement groups:

1. CLustered Placement Group: Low network latency/high network throughput, same AZ

2. Spread Placement Group: Individual Critical EC2 instances, each have separate hardware

3. Partitioned: For Multiple EC2 instances for HBase, HDFS and Cassandra

AWS recomments homogeneous instances within clustered placement groups

You cannot merge placement groups

#### You cant move existing instance into placement group but, but you can create AMI from existing instance and launch new instance from AMI into placement group


#### How to block malicious IP:

1. AWS WAF

2. NACLs
