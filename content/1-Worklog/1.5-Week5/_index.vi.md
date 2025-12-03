---
title: "Worklog Tuần 5"
date: 2025-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu Tuần 5:
* Hiểu và thực hành triển khai ứng dụng WordPress trên AWS bằng EC2, RDS và S3.  
* Học cách phân phối nội dung toàn cầu bằng Amazon CloudFront.  
* Thực hành triển khai và quản lý dịch vụ AWS Managed Microsoft AD.  
* Cấu hình IAM Federation và xác thực người dùng với AWS Managed AD.  

### Nhiệm vụ & Tiến độ:
| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --------- | ------------- | ---------------- | ------------------ |
| 2 | - Xem tổng quan lab triển khai WordPress <br> - Hiểu các thành phần: EC2, RDS, S3, Security Groups <br> - Chuẩn bị key pair và IAM role cho WordPress instance | 06/10/2025 | 06/10/2025 | <https://000101.awsstudygroup.com/> |
| 3 | - Triển khai WordPress trên AWS Cloud <br> + Khởi tạo EC2 và cấu hình Apache/PHP <br> + Tạo cơ sở dữ liệu MySQL trên RDS <br> + Kết nối WordPress với RDS <br> + Kiểm tra truy cập website <br> + Cấu hình S3 để lưu trữ media <br> + Dọn dẹp tài nguyên | 07/10/2025 | 07/10/2025 | <https://000101.awsstudygroup.com/> |
| 4 | - Xem lại nội dung AWS CloudFront Workshop <br> - Cấu hình CloudFront phân phối nội dung tĩnh cho WordPress <br> - Bật cache, HTTPS và cấu hình tên miền tùy chỉnh <br> - Kiểm tra hiệu suất website sau khi kích hoạt CloudFront | 08/10/2025 | 08/10/2025 | <https://000130.awsstudygroup.com/> |
| 5 | - Xem lab triển khai AWS Managed AD <br> - Hiểu quy trình: tạo VPC, subnet, cấu hình directory <br> - Triển khai AWS Managed AD và kiểm tra domain join từ EC2 | 09/10/2025 | 09/10/2025 | <https://000093.awsstudygroup.com/> |
| 6 | - Thực hành IAM Federation với AWS Managed AD <br> + Cấu hình quan hệ tin cậy (trust relationship) <br> + Tích hợp người dùng IAM và xác thực qua AD <br> + Kiểm tra đăng nhập bằng thông tin AD qua AWS Console <br> + Dọn dẹp toàn bộ tài nguyên | 10/10/2025 | 10/10/2025 | <https://000095.awsstudygroup.com/> |

### Kết quả đạt được:
* Triển khai thành công website WordPress trên AWS tích hợp với RDS và S3.  
* Cấu hình CloudFront để tăng tốc phân phối nội dung toàn cầu.  
* Triển khai và kiểm thử AWS Managed Microsoft AD trong môi trường VPC bảo mật.  
* Thiết lập thành công IAM Federation với AD để quản lý tập trung người dùng.  
* Dọn dẹp hoàn toàn tài nguyên và ghi chép quy trình triển khai chi tiết.  
