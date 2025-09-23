---
title: "Week 2 Worklog"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---


### Week 2 Objectives:

* Connect and get acquainted with members of First Cloud Journey.
* Understand basic AWS services, how to use the console & CLI.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Learn AWS Virtual Private Cloud <br>&emsp; + VPC Security and Multi-VPC features <br>&emsp; + VPC - DirecConnect - LoadBalancer - ExtraResources <br> - **Practice:** <br>&emsp; + Start with Amazon VPC and AWS VPN Site-to-Site <br>&emsp; + Subnets, Route table,Internet Gateway, Nat Gateway, Security Group, Network ACLs <br>&emsp; + Create VPC , VPC Resource Map, Create Subnet, Create an Internet Gateway, Create Route Table for Outbound Internet Routing via Internet Gateway, Create security groups <br>&emsp; + Create EC2 Instances in Subnets, Test connection, Create NAT Gateway, EC2 Instance Connect Endpoint              | 09/11/2025 | 09/16/2025      |  <br>https://000009.awsstudygroup.com/ |                                                                                                  | 08/11/2025 | 08/11/2025      |
| 3   | -  Set up Hybrid DNS with Route 53 Resolver <br>&emsp; + Generate Key Pair <br>&emsp; +  Initialize CloudFormation Template <br>&emsp; + Configure Security Group <br>&emsp; +  Connect to RDGW <br>                                              | 09/18/2025 | 09/18/2025      | https://000010.awsstudygroup.com/ |
| 4   | - Learn Hybrid DNS   <br> - **Practice:** <br>&emsp; + Set up DNS <br>&emsp; + Create Route 53 Outbound Endpoint <br> &emsp; + Create Route 53 Resolver Rules <br>&emsp; + Create Route 53 Inbound Endpoint <br>&emsp; + Test result <br>&emsp; + Clean up resources <br> | 09/19/2025 | 09/19/2025      | <https://000010.awsstudygroup.com/> |
| 5   | - Learn basic EC2: <br>&emsp; + Instance types and AMIs <br>&emsp; + EBS volumes <br>&emsp; + Elastic IP <br>&emsp; + Security Groups and Key Pairs <br> - SSH connection methods to EC2 <br> - Launch templates, auto-scaling basics | 09/20/2025 | 09/21/2025      | https://000004.awsstudygroup.com/vi/ |
| 6   | - **Practice:** <br>&emsp; + Launch EC2 instances with different instance types <br>&emsp; + Connect via SSH and test key pairs <br>&emsp; + Attach and mount EBS volumes <br>&emsp; + Associate Elastic IPs <br>&emsp; + Test security group rules and connectivity | 09/21/2025 | 09/21/2025      | https://000004.awsstudygroup.com/vi/ |


### Week 2 Achievements:

* Gained a clear understanding of AWS core service groups:
  * Compute (EC2, Lambda, Auto Scaling)
  * Storage (S3, EBS, EFS)
  * Networking (VPC, Route 53, VPN, Security Groups)
  * Database (RDS, DynamoDB)
  * Monitoring & Management (CloudWatch, CloudTrail)
* Successfully created and fully configured an AWS Free Tier account.
* Became familiar with the AWS Management Console: locating services, navigating dashboards, accessing features.
* Installed and configured AWS CLI with:
  * Access Key & Secret Key
  * Default Region
  * Output format
* Performed essential operations via CLI:
  * Check account information and configuration
  * List available regions
  * Launch and manage EC2 instances
  * Create and manage key pairs
  * Inspect running services and resources
* Practiced connecting and managing AWS resources through both the console and CLI in parallel.
* Learned practical networking and hybrid DNS setup with Route 53 Resolver.
* Successfully tested EC2 connectivity, NAT Gateway, and Elastic IP configurations.
* Developed foundational skills for automated infrastructure deployment with CloudFormation templates.
* Built confidence in troubleshooting common AWS networking and access issues.