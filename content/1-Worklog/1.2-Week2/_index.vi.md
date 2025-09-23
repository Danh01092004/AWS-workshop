---
title: "Worklog Tuần 2"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---


### Mục tiêu tuần 2:

* Kết nối, làm quen với các thành viên trong First Cloud Journey.
* Hiểu dịch vụ AWS cơ bản, cách dùng console & CLI.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Học về AWS Virtual Private Cloud (VPC) <br>&emsp; + Tính năng bảo mật VPC và Multi-VPC <br>&emsp; + VPC - DirectConnect - LoadBalancer - Tài nguyên bổ sung <br> - **Thực hành:** <br>&emsp; + Bắt đầu với Amazon VPC và AWS VPN Site-to-Site <br>&emsp; + Subnet, Bảng định tuyến, Internet Gateway, NAT Gateway, Security Group, Network ACLs <br>&emsp; + Tạo VPC, Bản đồ tài nguyên VPC, Tạo Subnet, Tạo Internet Gateway, Tạo Route Table cho định tuyến Internet Outbound qua Internet Gateway, Tạo Security Group <br>&emsp; + Tạo EC2 Instances trong Subnets, Kiểm tra kết nối, Tạo NAT Gateway, EC2 Instance Connect Endpoint | 11/09/2025 | 16/09/2025 |  <br>https://000009.awsstudygroup.com/               |
| 3   | -  Thiết lập Hybrid DNS với Route 53 Resolver <br>&emsp; + Tạo Key Pair <br>&emsp; + Khởi tạo CloudFormation Template <br>&emsp; + Cấu hình Security Group <br>&emsp; + Kết nối tới RDGW <br> | 18/09/2025 | 18/09/2025      | https://000010.awsstudygroup.com/ |
| 4   | - Học về Hybrid DNS   <br> - **Thực hành:** <br>&emsp; + Cấu hình DNS <br>&emsp; + Tạo Route 53 Outbound Endpoint <br> &emsp; + Tạo Route 53 Resolver Rules <br>&emsp; + Tạo Route 53 Inbound Endpoint <br>&emsp; + Kiểm tra kết quả <br>&emsp; + Dọn dẹp resources <br> | 19/09/2025 | 19/09/2025      | <https://000010.awsstudygroup.com/> |
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