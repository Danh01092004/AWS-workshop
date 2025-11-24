---
title: "Worklog Tuần 6"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---



### Mục tiêu tuần 6:

* Học cách thiết kế và triển khai kiến trúc **serverless** bằng các dịch vụ của AWS.
* Xây dựng và kiểm thử ứng dụng với **AWS Lambda**, **API Gateway** và **DynamoDB**.
* Tự động hóa việc triển khai hạ tầng bằng **AWS CloudFormation**.
* Khám phá thiết kế **event-driven** và khả năng tích hợp giữa các dịch vụ.
* Áp dụng các phương pháp giám sát (monitoring) và ghi log (logging) tốt nhất cho môi trường serverless.

---

### Nhiệm vụ cần thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | ---- | ----------- | ---------------- | ------------------ |
| 2 | - Tìm hiểu khái niệm và lợi ích của **Serverless Computing**. <br> - Hiểu khi nào nên dùng **Lambda** thay vì **EC2**. <br> - **Thực hành:** <br> &emsp;+ Tạo một hàm **Lambda** đơn giản bằng Python. <br> &emsp;+ Kiểm thử kích hoạt hàm qua **AWS Console** và **CLI**. <br>| 13/10/2025 | 13/10/2025 | AWS Study Group |
| 3 | - Học cách xây dựng **API** bằng **Amazon API Gateway**. <br> - **Thực hành:** <br> &emsp;+ Tạo một REST API endpoint liên kết với Lambda. <br> &emsp;+ Triển khai các giai đoạn (stage) API và kiểm thử truy cập công khai. <br>| 14/10/2025 | 14/10/2025 | AWS Study Group |
| 4 | - Làm việc với **Amazon DynamoDB** cho lưu trữ dữ liệu serverless. <br> - **Thực hành:** <br> &emsp;+ Tạo bảng DynamoDB và định nghĩa **Partition Key** / **Sort Key**. <br> &emsp;+ Kết hợp Lambda để thực hiện các thao tác **CRUD**. <br> &emsp;+ Kiểm thử truy xuất và cập nhật dữ liệu thông qua API Gateway. <br>| 15/10/2025 | 15/10/2025 |AWS Study Group |
| 5 | - Tìm hiểu cơ bản về **AWS CloudFormation** cho **Hạ tầng dưới dạng mã (IaC)**. <br> - **Thực hành:** <br> &emsp;+ Viết tệp YAML để triển khai Lambda, API Gateway và DynamoDB. <br> &emsp;+ Tự động hóa việc tạo và xóa stack. <br>| 16/10/2025 | 16/10/2025 | AWS Study Group |
| 6 | - Thực hiện **giám sát (monitoring)** và **tự động hóa (automation)** cho hệ thống serverless. <br> - **Thực hành:** <br> &emsp;+ Sử dụng **CloudWatch Logs** để theo dõi hoạt động của Lambda. <br> &emsp;+ Thiết lập **CloudWatch Alarms** để phát hiện lỗi và throttles. <br> &emsp;+ Tạo một quy tắc tự động đơn giản bằng **EventBridge**. <br>| 17/10/2025 | 17/10/2025 | AWS Study Group |

---

### Thành tựu đạt được trong tuần 6:

* **Kiến thức nền tảng về Serverless**  
  Hiểu rõ lợi ích của thiết kế không máy chủ như: không cần quản lý máy chủ, tự động mở rộng, và thanh toán theo mức sử dụng.  
  Đã tạo và kiểm thử các hàm **Lambda** cơ bản, được kích hoạt thủ công và qua các sự kiện API.

* **Tích hợp với API Gateway**  
  Xây dựng **REST API** bằng **Amazon API Gateway** và liên kết trực tiếp với **Lambda**.  
  Triển khai nhiều môi trường (dev, prod) và kiểm thử truy cập công khai thành công.

* **Tích hợp DynamoDB**  
  Thiết kế bảng **DynamoDB** với cấu trúc khóa hiệu quả cho truy xuất nhanh.  
  Tích hợp Lambda để thực hiện các thao tác **CRUD** trực tiếp từ hàm serverless.  
  Kiểm thử thành công quy trình **API → Lambda → DynamoDB** từ đầu đến cuối.

* **Hạ tầng dưới dạng mã (Infrastructure as Code - IaC)**  
  Tự động hóa việc triển khai kiến trúc serverless bằng **CloudFormation templates**.  
  Quản lý việc tạo, cập nhật, và xóa stack một cách có thể tái sử dụng và kiểm soát được.

* **Giám sát và Tự động hóa**  
  Sử dụng **CloudWatch Logs** và **CloudWatch Alarms** để phát hiện sự cố trong quá trình chạy.  
  Dùng **EventBridge** để kích hoạt cảnh báo hoặc quy trình tự động dựa trên các sự kiện từ Lambda.

