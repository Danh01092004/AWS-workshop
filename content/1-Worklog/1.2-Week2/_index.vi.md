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
| 2   | - Học về AWS Virtual Private Cloud (VPC) <br>&emsp; + Tính năng bảo mật VPC và Multi-VPC <br>&emsp; + VPC - DirectConnect - LoadBalancer - Tài nguyên bổ sung <br> - **Thực hành:** <br>&emsp; + Bắt đầu với Amazon VPC và AWS VPN Site-to-Site <br>&emsp; + Subnet, Bảng định tuyến, Internet Gateway, NAT Gateway, Security Group, Network ACLs <br>&emsp; + Tạo VPC, Bản đồ tài nguyên VPC, Tạo Subnet, Tạo Internet Gateway, Tạo Route Table cho định tuyến Internet Outbound qua Internet Gateway, Tạo Security Group <br>&emsp; + Tạo EC2 Instances trong Subnets, Kiểm tra kết nối, Tạo NAT Gateway, EC2 Instance Connect Endpoint | 11/09/2025 | 16/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | -  Thiết lập Hybrid DNS với Route 53 Resolver <br>&emsp; + Tạo Key Pair <br>&emsp; + Khởi tạo CloudFormation Template <br>&emsp; + Cấu hình Security Group <br>&emsp; + Kết nối tới RDGW <br> | 19/09/2025 | 19/09/2025      | https://000010.awsstudygroup.com/ |
| 4   | - Tạo AWS Free Tier account <br> - Tìm hiểu AWS Console & AWS CLI <br> - **Thực hành:** <br>&emsp; + Tạo AWS account <br>&emsp; + Cài AWS CLI & cấu hình <br> &emsp; + Cách sử dụng AWS CLI | 13/08/2025   | 13/08/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu EC2 cơ bản: <br>&emsp; + Instance types <br>&emsp; + AMI <br>&emsp; + EBS <br>&emsp; + ... <br> - Các cách remote SSH vào EC2 <br> - Tìm hiểu Elastic IP   <br>                  | 14/08/2025   | 15/08/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Thực hành:** <br>&emsp; + Tạo EC2 instance <br>&emsp; + Kết nối SSH <br>&emsp; + Gắn EBS volume                                                                                         | 15/08/2025   | 15/08/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 2:

* Hiểu AWS là gì và nắm được các nhóm dịch vụ cơ bản: 
  * Compute
  * Storage
  * Networking 
  * Database
  * ...

* Đã tạo và cấu hình AWS Free Tier account thành công.

* Làm quen với AWS Management Console và biết cách tìm, truy cập, sử dụng dịch vụ từ giao diện web.

* Cài đặt và cấu hình AWS CLI trên máy tính bao gồm:
  * Access Key
  * Secret Key
  * Region mặc định
  * ...

* Sử dụng AWS CLI để thực hiện các thao tác cơ bản như:

  * Kiểm tra thông tin tài khoản & cấu hình
  * Lấy danh sách region
  * Xem dịch vụ EC2
  * Tạo và quản lý key pair
  * Kiểm tra thông tin dịch vụ đang chạy
  * ...

* Có khả năng kết nối giữa giao diện web và CLI để quản lý tài nguyên AWS song song.
* ...


