---
title: "Worklog Tuần 4"
date: 2025-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---



### Mục tiêu tuần 4:
* Hiểu và thực hành làm việc với Amazon S3 (hosting website tĩnh, cấu hình, bảo mật, versioning, CloudFront).  
* Hiểu và thực hành Amazon RDS (tạo database, backup/restore, cấu hình VPC/Subnet/SG, cleanup) theo lab.  
* Kết hợp giữa giao diện AWS Console và CLI để quản lý tài nguyên S3 & RDS.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                 | Start Date | Completion Date | Reference Material                                                  |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------------------------------- |
| 2   | - Đọc tổng quan lab S3: các bước tạo bucket, bật website tĩnh, cấu hình public access, versioning, dọn dẹp tài nguyên <br> - Chuẩn bị tài khoản AWS & đảm bảo quyền truy cập S3 | 29/09/2025 | 29/09/2025      | <https://000057.awsstudygroup.com/vi/>  |
| 3   | - Khởi Đầu Với Amazon S3: <br>&emsp; + Tạo S3 bucket <br>&emsp; + Upload dữ liệu <br>&emsp; + Bật tính năng static website <br>&emsp; + Cấu hình Block Public Access <br>&emsp; + Cấu hình public object <br>&emsp; + Kiểm tra website <br>&emsp; + Cấu hình CloudFront để tăng tốc hosting <br>&emsp; + Bật versioning cho bucket <br>&emsp; + Sao chép object sang region khác <br>&emsp; + Dọn dẹp tài nguyên | 30/09/2025 | 30/09/2025      | <https://000057.awsstudygroup.com/vi/> |
| 4   | - Đọc tổng quan lab RDS: các bước tạo VPC, Subnet, Security Group, tạo DB instance, backup & restore, dọn dẹp tài nguyên <br> - Chuẩn bị cấu hình mạng (VPC, subnet) cho lab | 01/10/2025 | 01/10/2025      | <https://000005.awsstudygroup.com/vi/>|
| 5   | - Bắt đầu với Amazon RDS: <br>&emsp; + Tạo VPC <br>&emsp; + Tạo EC2 security group <br>&emsp; + Tạo RDS security group <br>&emsp; + Tạo DB Subnet Group <br>&emsp; + Tạo EC2 instance (nếu cần để kết nối) <br>&emsp; + Tạo RDS database instance <br>&emsp; + Thực hành backup & restore DB instance <br>&emsp; + Kiểm tra endpoint DB, quyền truy cập <br>&emsp; + Dọn dẹp tài nguyên (delete DB, SG, Subnet group) | 02/10/2025 | 02/10/2025      | <https://000005.awsstudygroup.com/vi/>  |
| 6 | - Thực hành các lệnh AWS CLI cho S3 và RDS: <br> + Tạo và liệt kê các bucket S3 bằng CLI <br> + Tải lên/tải xuống đối tượng bằng CLI <br> + Mô tả và kết nối tới RDS instance bằng CLI <br> - Ghi lại sự khác biệt giữa quy trình trên Console và CLI | 03/10/2025 | 03/10/2025 | <https://000057.awsstudygroup.com/vi/>, <https://000005.awsstudygroup.com/vi/> |

### Week Achievements:

* Hiểu rõ cấu trúc và bước để host website tĩnh trên S3: tạo bucket, cấu hình public access, bật website, cấu hình CloudFront để tăng tốc.  
* Nắm được cách bật versioning cho bucket và cách sao chép object giữa region.  
* Thực hành xóa tài nguyên S3 đúng cách để không phát sinh chi phí.  
* Hiểu khái niệm RDS: cách tạo VPC, Subnet, Security Group, DB Subnet Group.  
* Tạo DB instance RDS thành công, truy cập được endpoint, thực hiện backup và restore.  
* Biết cách dọn dẹp tài nguyên RDS (xóa DB, Subnet Group, Security Group) sau khi lab.  
* So sánh và nhận ra những ưu/nhược điểm khi thao tác qua giao diện AWS Console so với việc dùng AWS CLI (tiện lợi, lặp lại, script hóa).  
