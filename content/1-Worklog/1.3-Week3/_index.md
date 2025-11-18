---
title: "Week 3 Worklog"
date: 2025-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---



### Week 3 Objectives:

* Learn and practice with Amazon VPC (basic networking, subnets, route tables, security groups).  
* Get hands-on with EC2 instances: launch, connect via SSH, attach storage.  
* Understand EBS, Elastic IP, and Security Group configurations.  
* Combine AWS Console and CLI to manage EC2 networking and storage resources.  

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                  | Start Date | Completion Date | Reference Material                        |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ----------------------------------------- |
| 2 | - Read through prerequisites in lab guide <br> - Understand AWS global infrastructure (Regions, AZs, VPC) <br> - Review basic networking concepts (subnets, route tables, gateways) | 09/22/2025 | 09/22/2025 | <https://000003.awsstudygroup.com/vi/> |
| 3 | - Learn how to create a custom VPC <br>&emsp; + Define CIDR block <br>&emsp; + Add public & private subnets <br>&emsp; + Configure route tables & internet gateway <br>&emsp; + Associate subnets | 09/23/2025 | 09/23/2025 | <https://000004.awsstudygroup.com/vi/> |
| 4 | - Explore EC2 networking: <br>&emsp; + Security Groups (inbound & outbound rules) <br>&emsp; + Key pairs for SSH <br> - Prepare environment for launching Linux EC2 instance | 09/24/2025 | 09/24/2025 | <https://000004.awsstudygroup.com/vi/> |
| 5 | - Practice EC2 launch: <br>&emsp; + Choose AMI (Amazon Linux/Ubuntu) <br>&emsp; + Select instance type (t2.micro) <br>&emsp; + Configure networking (VPC, subnet, SG) <br>&emsp; + Assign Elastic IP <br> - Test SSH connectivity | 09/25/2025 | 09/25/2025 | <https://000004.awsstudygroup.com/vi/> |
| 6 | - Work with storage: <br>&emsp; + Create and attach additional EBS volume <br>&emsp; + Format and mount the volume <br> - Verify instance status & connectivity via Console & CLI <br> - Cleanup resources (terminate EC2, release Elastic IP, delete volumes) | 09/26/2025 | 09/26/2025 | <https://000004.awsstudygroup.com/vi/> |

### Week 3 Achievements:

* Understood AWS global infrastructure (Regions, AZs, and VPC).  
* Successfully created a custom VPC with subnets, route tables, and an internet gateway.  
* Learned to configure Security Groups and manage inbound/outbound rules.  
* Launched a Linux EC2 instance with proper networking setup.  
* Practiced connecting to EC2 via SSH using key pairs.  
* Assigned and tested Elastic IP for stable public access.  
* Attached, formatted, and mounted an EBS volume to extend storage.  
* Verified instance status and resources using both AWS Console and CLI.  
* Practiced proper cleanup: terminating EC2, releasing Elastic IP, and deleting EBS volumes.  
* Built solid foundational skills for AWS networking (VPC) and compute (EC2).  
