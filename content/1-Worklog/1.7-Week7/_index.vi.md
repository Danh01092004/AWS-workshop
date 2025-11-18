---
title: "Worklog Tuần 7"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---



### Mục tiêu Tuần 7:

* Hiểu khái niệm và lợi ích của **containerization** trong phát triển ứng dụng.  
* Học cách **xây dựng, quản lý và triển khai Docker container**.  
* Khám phá **Amazon ECS (Elastic Container Service)** và **ECR (Elastic Container Registry)**.  
* Triển khai ứng dụng web dưới dạng container bằng **ECS Fargate**.  
* Làm quen với **CI/CD tự động hóa** cho quy trình triển khai container.  

---

### Nhiệm vụ thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | ---- | ----------- | ---------------- | ------------------ |
| 2 | - Ôn lại sự khác biệt giữa **Container** và **Máy ảo (VM)**. <br> - Tìm hiểu vai trò của **Docker** trong đóng gói và cách ly ứng dụng. <br> - **Thực hành:** <br>&emsp; + Cài đặt Docker Desktop. <br>&emsp; + Tạo Dockerfile cho ứng dụng web đơn giản (Node.js hoặc Python Flask). <br>&emsp; + Build và chạy container cục bộ. <br><br> → Nắm vững kiến thức thực hành về containerization. | 20/10/2025 | 20/10/2025 | AWS Study Group |
| 3 | - Tìm hiểu về **Amazon Elastic Container Registry (ECR)**. <br> - **Thực hành:** <br>&emsp; + Tạo repository trên ECR. <br>&emsp; + Gắn thẻ và đẩy image Docker lên ECR. <br>&emsp; + Kiểm tra lưu trữ và quyền truy cập image. <br><br> → Hiểu cách quản lý image trong AWS. | 21/10/2025 | 21/10/2025 | AWS Study Group |
| 4 | - Khám phá kiến thức cơ bản về **Amazon Elastic Container Service (ECS)**. <br> - **Thực hành:** <br>&emsp; + Tạo ECS Cluster sử dụng loại khởi chạy Fargate. <br>&emsp; + Định nghĩa Task Definitions và Services. <br>&emsp; + Triển khai ứng dụng containerized. <br><br> → Học cách điều phối (orchestrate) container trong AWS. | 22/10/2025 | 22/10/2025 | AWS Study Group |
| 5 | - Tích hợp **Load Balancer** với ECS. <br> - **Thực hành:** <br>&emsp; + Cấu hình Application Load Balancer (ALB). <br>&emsp; + Kết nối dịch vụ ECS với ALB để truy cập công khai. <br>&emsp; + Kiểm tra khả năng mở rộng và tính sẵn sàng cao. <br><br> → Đảm bảo khả năng mở rộng và tính ổn định của ứng dụng container. | 23/10/2025 | 23/10/2025 | AWS Study Group |
| 6 | - Tự động hóa quy trình triển khai bằng **AWS CodePipeline** và **CodeBuild**. <br> - **Thực hành:** <br>&emsp; + Thiết lập pipeline CI/CD để build image Docker. <br>&emsp; + Tự động triển khai bản cập nhật lên ECS. <br>&emsp; + Kiểm tra triển khai không gián đoạn (zero downtime). <br><br> → Xây dựng quy trình tự động hóa triển khai liên tục. | 24/10/2025 | 24/10/2025 | AWS Study Group |

---

### Kết quả đạt được trong Tuần 7:

* **Kiến thức nền tảng về Docker**  
  - Hiểu sự khác biệt giữa container và máy ảo, lý do container nhẹ và linh hoạt hơn.  
  - Tạo và kiểm thử container Docker cục bộ bằng Dockerfile tự viết.  

* **Quản lý image với ECR**  
  - Tạo và quản lý repository riêng trên Amazon ECR.  
  - Đẩy (push) và tải (pull) image Docker thành công từ ECR.  

* **Triển khai với ECS**  
  - Xây dựng và triển khai ứng dụng containerized bằng ECS Fargate.  
  - Cấu hình Task Definition, Service và thiết lập mạng cho ứng dụng ECS.  

* **Cân bằng tải và mở rộng hệ thống**  
  - Tích hợp **Application Load Balancer (ALB)** với dịch vụ ECS để truy cập công khai.  
  - Kiểm chứng khả năng mở rộng tự động và phân phối lưu lượng giữa các container.  

* **Tự động hóa CI/CD**  
  - Thiết lập pipeline CI/CD sử dụng **CodePipeline** và **CodeBuild**.  
  - Tự động build và triển khai image lên ECS.  
  - Đạt được triển khai hiệu quả, lặp lại được và không gián đoạn (zero downtime).  
