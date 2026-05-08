# 30 Days AWS Zero to Hero

## Prerequisites:
1. Windows/ Mac laptop
2. Basic Linux Commands

## Day 1: AWS Overview
Understanding the fundamentals of cloud computing, focusing on AWS's global infrastructure and account creation.
- What is Cloud Computing?
- Benefits of Cloud Computing
- Types of Cloud Computing
- Types of Cloud Services
- What is AWS?
- Advantages of AWS
- Disadvantages of AWS
- AWS Global Infrastructure
- Regions
- Availability Zones
- Lab Session - Creation of an AWS account

## Day 2: Amazon Elastic Compute Cloud (EC2) Part 1
Introduction to Amazon EC2 instances, including instance types and basic management tasks like instance creation and connectivity setup.
- What is Amazon EC2?
- Features of Amazon EC2
- Amazon EC2 Instance Types
- Lab Session - Creation of a Linux EC2 instance
- Lab Session - Downloading PuTTY and PuTTYgen
- Lab Session - Convert PEM to PPK file
- Lab Session - Connecting to Linux server
- Lab Session - Creation of a Windows EC2 instance
- Lab Session - Create an AMI from an Amazon EC2 Instance

## Day 3: Amazon Elastic Compute Cloud (EC2) Part 2
Exploring advanced EC2 concepts like Elastic IPs, Security Groups, and various purchasing options for instances.

- Lab Session - Creation of a Ubuntu EC2 instance
- What is an Elastic IP?
- Lab Session - Creating an Elastic IP and Attaching it to an EC2 Instance
- What is a Security Group?
- Lab Session - Creating a Security Group and Attaching it to an EC2 Instance
- Spot Instances, On-Demand Instances, Savings Plans, Reserved Instances, Dedicated Hosts, Scheduled Instances, Capacity Reservations
- Lab Session - Opening a support ticket with AWS
- Lab Session - Requesting Service Quotas in AWS
- Lab Session - Metadata and user data in EC2

## Day 4: AWS EBS (Elastic Block Storage)
Detailed look into AWS EBS volumes, including creation, resizing, and encryption of volumes.
- What is AWS EBS?
- Features of AWS EBS
- Types of EBS Volumes
- Lab Session - Creation of an EBS Volume
- Lab Session - Attach an EBS volume to a Linux EC2 instance
- Lab Session - Increase the size of an existing EBS volume on a Linux EC2 instance
- Lab Session - Attach an EBS volume to a Windows EC2 instance
- Lab Session - Increase the size of an existing EBS volume on a Windows EC2 instance
- Lab Session - Change the EBS volume type

## Day 5: AWS EBS Snapshot
Understanding snapshots in AWS, including creation, management, and utilization for backups and AMI creation.
- What is a Snapshot in AWS?
- Lab Session - Creation of a snapshot from an EBS volume
- Lab Session - Creation of an AWS AMI from a snapshot
- Lab Session - Creation of an EBS volume from a snapshot
- Options in a Snapshot
- Lab Session - Deletion of Snapshots, Volumes, and AMIs

## Day 6: AWS IAM (Identity Access Management)
Learning AWS IAM basics, user management, policies, roles, and best practices for secure account management.
- What is AWS IAM?
- Features of AWS IAM
- Lab Session - AWS IAM Users
- Lab Session - AWS IAM User Groups
- What are AWS IAM Policies?
- Types of AWS IAM Policies
- Lab Session - Configuring AWS CLI
- Lab Session - Named profiles for the AWS CLI
- What is an IAM role?
- Lab Session - How to attach the IAM role to an EC2 instance?
- Root Account vs IAM user
- Lab Session - AWS IAM Password Policy
- Lab Session - Multi-Factor Authentication (MFA) for AWS IAM
- IAM Best Practices

## Day 7: AWS ASG (Auto Scaling Group)
Exploring auto-scaling concepts, including Launch Configurations, Launch Templates, and integration with CloudWatch.
- What is an Auto Scaling Group?
- Benefits of an Auto Scaling Group
- What is a Launch Configuration?
- Benefits of a Launch Configuration
- Drawbacks of a Launch Configuration
- Lab Session - Creation of an AWS Launch Configuration
- What is an AWS Launch Template?
- Benefits of an AWS Launch Template
- Lab Session - Creation of an AWS Launch Template
- Difference between a Launch Template and a Launch Configuration
- Lab Session - Creation of an ASG through an AWS Launch Configuration
- Lab Session - Creation of an ASG through an AWS Launch Template
- Lab Session - Enabling CloudWatch monitoring in an ASG
- Lab Session - Deletion of an ASG

## Day 8: AWS ELB (Elastic Load Balancing)
Introduction to AWS ELB services, including Classic Load Balancers, Application Load Balancers, and Network Load Balancers.

- What is AWS Elastic Load Balancing?
- Benefits of AWS Elastic Load Balancing
- What is an AWS Classic Load Balancer?
- Features of a Classic Load Balancer
- Lab Session - Creation of an AWS Classic Load Balancer
- Lab Session - Deletion of a Classic Load Balancer
- What is an AWS Target Group?
- What is a Listener?
- Lab Session - Creation of an AWS Target Group

## Day 9: AWS ELB (Elastic Load Balancing) Part 2
Advanced ELB configurations and differences between ALB and NLB, with practical sessions on integration with ASGs.
- What is an AWS Application Load Balancer?
- Benefits of an AWS Application Load Balancer
- Lab Session - Creation of an Application Load Balancer
- Lab Session - Attaching an ALB to a new Auto Scaling group
- Lab Session - Deletion of an ALB
- What is an AWS Network Load Balancer?
- Benefits of an AWS Network Load Balancer
- Lab Session - Creation of an AWS Network Load Balancer
- Lab Session - Deletion of an NLB
- Difference between an ALB and an NLB
- Lab Session - Attaching an NLB  to an Auto Scaling group

## Day 10: AWS S3 (Simple Storage Service)
Understanding AWS S3 fundamentals, including bucket creation, object storage, versioning, and access control.

- What is AWS Simple Storage Service (S3)?
- Buckets and Objects in Amazon S3
- Types of storage classes in AWS S3
- Lab Session - Create an S3 bucket
- Lab Session - Upload objects to S3 using the AWS Console
- Lab Session - Upload objects to S3 using the AWS CLI
- S3 Versioning and enabling it
## Day 11: AWS S3 Part 2
- Bucket Policy in Amazon S3
- Working with the Bucket Policy for S3 bucket
- S3 Bucket Lifecycle
- Hosting a static website using Amazon S3
- Presigned URLs in AWS S3
- Lab Session - Working with Presigned URLs in AWS S3
- Server-side encryption for Amazon S3 buckets
- Lab Session - Delete an S3 bucket

## Day 12: AWS VPC (Virtual Private Cloud) Part 1
Introduction to AWS VPC networking, including CIDR blocks, subnets, route tables, and internet gateway setup.
- What is AWS VPC (Virtual Private Cloud)?
- Key features of AWS VPC
- CIDR (Classless Inter-Domain Routing)
- Lab Session - Choose the appropriate CIDR Block
- IPV4 and IPV6
- Subnets in AWS VPC
- Types of Subnets in AWS VPC
- Subnet sizing for IPV4
- Subnet routing in AWS VPC
- Route table in AWS VPC
- Components of a Route table
- Internet Gateway (IGW) in AWS VPC
- Lab Session - Overview of the Default VPC in AWS

## Day 13: AWS VPC (Virtual Private Cloud) Part 2
Advanced VPC configurations including NAT instances, NAT gateways, NACLs, and Security Groups.

- Corporate  AWS VPC Architecture and Best Practices
- Lab Session - Create a customized VPC in AWS
- NAT Gateway and NAT Instance in AWS VPC
- Differences between NAT Gateway and NAT Instance
- Lab Session - Create a NAT Instance in AWS VPC
- Lab Session - Create a NAT Gateway in AWS VPC
- Lab Session - Delete a NAT Gateway in AWS VPC

## Day 14: AWS VPC (Virtual Private Cloud) Part 3
Exploring VPC Flow Logs, DHCP options, VPC endpoints, and Elastic Network Interfaces (ENIs).
- Network Access Control List (NACL) in AWS VPC
- Lab Session - Create a Network Access Control List (NACL) in AWS VPC
- Security Group in AWS VPC
- Lab Session - Create a Security Group in AWS VPC
- Differences between NACL and Security Group in AWS VPC
- VPC Flow Logs and how to create them
- Lab Session - Enable VPC Flow Logs

## Day 15: AWS VPC (Virtual Private Cloud) Part 4
Advanced VPC options like DNS settings, Prefix Lists, and deletion procedures for custom VPC setups.
- Options for configuring an AWS VPC
- DHCP Option Set in AWS VPC
- DNS Hostnames and DNS Resolution in AWS VPC
- VPC Endpoints in AWS and types available
- Lab Session - Create a Gateway VPC Endpoint for S3 in AWS
- Prefix Lists in AWS VPC
- Elastic Network Interface (ENI) in AWS
- Lab Session - Create an ENI in AWS
- Lab Session - Delete an AWS VPC

## Day 16: AWS VPC Peering
Understanding VPC peering within and between regions, including setup, management, and termination.

- What is VPC Peering?
- Key aspects of VPC Peering
- Types of VPC Peering
- Lab Session - Intra-region VPC peering within the same AWS account
- Lab Session - Delete intra-region VPC peering within the same AWS account
- Lab Session - Establish intra-region VPC peering with a different AWS account
- Lab Session - Terminate intra-region VPC peering with a different AWS account
- Lab Session - Inter-region VPC peering within the same AWS account
- Lab Session - Remove inter-region VPC peering within the same AWS account
- Lab Session - Configure inter-region VPC peering with a different AWS account
- Lab Session - Remove inter-region VPC peering with a different AWS account

## Day 17: AWS CloudWatch and CloudTrail
Introduction to AWS monitoring with CloudWatch, log management, and auditing with CloudTrail.

- What is CloudWatch?
- Key Features of CloudWatch
- Lab Session - Creating a log group in AWS CloudWatch
- Lab Session - Sending VPC Flow logs to a CloudWatch log group
- Lab Session - Setting up a CloudWatch alarm for an EC2 Instance
- What is AWS CloudTrail?
- Log event types in CloudTrail
- Lab Session - Setting up AWS CloudTrail to send logs to an S3 bucket
- Lab Session - Deletion of CloudTrail

## Day 18: AWS ECR (Elastic Container Registry)
Managing Docker images with AWS ECR, including repository creation, image pushing, and lifecycle policies.

- What is AWS ECR?
- Types of Repositories
- Components of Amazon ECR
- Features of Amazon ECR
- Lab Session - Creating an ECR repository in AWS
- Lab Session - Pushing a docker image to AWS ECR
- Lab Session - Setting up Lifecycle Policy in ECR
- Lab Session - Setting up Replication configuration in ECR

## Day 19: AWS EKS (Elastic Kubernetes Service)
Introduction to Kubernetes on AWS with EKS, including cluster setup, management, and application deployment.

- What is Amazon Elastic Kubernetes Service?
- How does Amazon EKS work?
- Lab Session - Creating an EKS Cluster through the AWS Console
- Lab Session - Connecting to the EKS cluster

## Day 20: AWS KMS , SES , SNS
Exploring AWS KMS for key management and encryption tasks, including key creation and usage scenarios.

- What is AWS KMS?
- Features and benefits of KMS
- Different types of keys in KMS
- Lab Session - Creating a KMS key
- Lab Session - Encrypting an EBS volume using AWS KMS
- Lab Session - Deletion of KMS
- What is AWS SES?
- Lab Session - Creating AWS SES
- Lab Session - Deletion of AWS SES
- What is AWS SNS?
- Lab Session - Creating AWS SNS
- Lab Session - Deletion of AWS SNS

## Day 21: AWS RDS (Relational Database Service).
Managing relational databases with AWS RDS, including instance creation, connectivity setup, and parameter group configuration.

- What is RDS?
- Features of RDS
- RDS Subnet Group
- Parameter groups
- Option groups
- Amazon RDS storage types
- Lab Session - Creating a MySQL database in AWS RDS
- Lab Session - Connecting to the RDS MySQL from an AWS EC2 instance
- Lab Session - Installation of MySQL Workbench
- Lab Session - Connecting to the RDS MySQL from MySQL Workbench
- Lab Session - Deletion of RDS MySQL version

## Day 22: AWS Route53
Introduction to AWS Route53 for DNS management, including hosted zones, records, routing policies.

- What is AWS Route53?
- Benefits of Route53
- What is a hosted zone in Route53?
- Types of hosted zones
- Lab Session - Creating a public hosted zone in AWS Route53
- What are records in a hosted zone?
- Types of records
- What is Routing Policy?
- Types of Routing policies
- Lab Session - Creating a record in a hosted zone
- Lab Session - Creating a private hosted zone in AWS Route53
- Lab Session - Configuring query logging for a Hosted Zone
- Lab Session - Deletion of a Hosted Zone

## Day 23: AWS ACM (AWS Certificate Manager)
Managing SSL/TLS certificates with AWS ACM, including integration with AWS services and certificate lifecycle management.

- What is AWS ACM?
- Lab Session - Creating AWS ACM
- Lab Session - Integrating AWS ACM with an Application Load Balancer
- Lab Session - Deletion of AWS ACM

## Day 24: AWS WAF (Web Application Firewall)
Introduction to AWS WAF for protecting web applications, including rules creation and application to ALB.

- What is AWS WAF?
- How AWS WAF works
- Creating a Web ACL
- Applying the Web ACL to an ALB
- Blocking a Specific IP Address

## Day 25: AWS EFS (Elastic File System)
Managing file storage with AWS EFS, including creation, mounting, and deletion of file systems.

- What is AWS EFS?
- Use cases of AWS EFS
- Types of AWS EFS Storage Classes
- Lab Session - Creation of AWS EFS
- Lab Session - Mounting AWS EFS in an EC2 instance
- Lab Session - Deletion of AWS EFS

## Day 26: AWS Systems Manager and Secret Manager
Overview of AWS Systems Manager for managing EC2 instances, including Patch Manager, Parameter Store, and Run Command.

- What is AWS Systems Manager?
- Supported operating systems and machine types
- What is SSM Agent?
- Working with SSM Agent
- What is Parameter Store?
- Creating the Parameter Store
- What is Secret Manager?
- Working with Secret Manager

## Day 27: AWS Calculator

Understanding AWS pricing with the AWS Calculator tool, estimating costs for various AWS services.

- Introduction to AWS Calculator
- Overview of AWS Pricing
- Basic Navigation and Interface
- Cost Estimation for EC2 Instances, EBS, RDS
- Practical Exercises with Different Instance Types

## Day 28: AWS Billing and Cost Management
Managing AWS costs and budgets with AWS Billing and Cost Management, setting up alerts and monitoring usage.

- What is AWS Billing and Cost Management?
- Features of AWS Billing and Cost Management
- Getting set up with Billing
- Setting up a budget

## Day 29: AWS Directory Service
Introduction to AWS Directory Service for managing user directories, including setup and basic management tasks.

- What is AWS Directory Service?
- AWS Directory Service options
- Getting started with AWS Managed Microsoft AD
- AWS Managed Microsoft AD prerequisites
- Create your AWS Managed Microsoft AD
- Deploy an Amazon EC2 instance to manage your AWS Managed Microsoft AD Active Directory
- Verify that the base test lab is operational

## Day 30: AWS Lambda 
- What is AWS Lambda
- Why Use AWS Lambda?
- Supported Runtimes
- Limitations
- Automated AMI Backups for EC2 Instances Using Lambda

# Conclusion
Congratulations on completing the "30 Days AWS Zero to Hero" curriculum! By now, you should have a solid foundation in AWS services and be ready to tackle more advanced topics and certifications.
