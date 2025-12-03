---
title: "Worklog Tuần 9"
date: 2025-01-01
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---


### Mục tiêu Tuần 9:

* Học cách thiết kế CI/CD pipeline an toàn và có khả năng mở rộng.
* Xây dựng quy trình triển khai ứng dụng bằng AWS CodePipeline, CodeBuild và CodeDeploy.
* Tích hợp GitHub hoặc CodeCommit làm nguồn mã.
* Tự động hóa việc triển khai ứng dụng lên EC2 và Lambda.
* Tăng cường bảo mật pipeline và thêm các bước kiểm thử tự động.

### Các nhiệm vụ thực hiện trong tuần:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ----- | ---------- | --------------- | ------------------ |
| 2 | - Tìm hiểu khái niệm CI/CD trên AWS.<br> - Hiểu cách CodePipeline điều phối các bước build → test → deploy.<br> - **Thực hành:** <br>&emsp; + Tạo một CodePipeline đơn giản với GitHub làm nguồn mã.<br>| 03/11/2025 | 03/11/2025 | AWS Study Group |
| 3 | - Học AWS CodeBuild để build và kiểm thử ứng dụng.<br> - **Thực hành:** <br>&emsp; + Viết file buildspec.yml.<br>&emsp; + Chạy build tự động và unit test.<br>| 04/11/2025 | 04/11/2025 | AWS Study Group |
| 4 | - Làm việc với AWS CodeDeploy để tự động triển khai ứng dụng.<br> - **Thực hành:** <br>&emsp; + Tạo deployment group cho EC2.<br>&emsp; + Triển khai ứng dụng bằng AppSpec.<br>&emsp; + Thử triển khai in-place và blue/green.<br>| 05/11/2025 | 05/11/2025 | AWS Study Group |
| 5 | - Tích hợp triển khai Lambda vào CodePipeline.<br> - **Thực hành:** <br>&emsp; + Deploy hàm Lambda bằng CodeDeploy.<br>&emsp; + Kiểm thử chiến lược triển khai Linear và Canary.<br>| 06/11/2025 | 06/11/2025 | AWS Study Group |
| 6 | - Thêm bảo mật và giám sát cho pipeline.<br> - **Thực hành:** <br>&emsp; + Bật CloudWatch và SNS notifications.<br>&emsp; + Cấu hình IAM cho từng stage trong pipeline.<br>&emsp; + Thêm bước test/approval để triển khai an toàn hơn.<br>| 07/11/2025 | 07/11/2025 | AWS Study Group |

### Thành tựu Tuần 9:

* **Kiến thức nền tảng về CI/CD Pipeline**
  * Hiểu quy trình CI/CD: source → build → test → deploy.
  * Xây dựng thành công CodePipeline đầu tiên tích hợp GitHub.

* **Tự động hóa Build (CodeBuild)**
  * Viết đầy đủ file buildspec.yml phục vụ build & test tự động.
  * Chạy build thành công trong môi trường cách ly của CodeBuild.

* **Tự động triển khai (CodeDeploy)**
  * Cấu hình deployment group cho EC2 và triển khai theo kiểu In-place & Blue/Green.
  * Hiểu rõ vai trò của AppSpec và các lifecycle hook.

* **Triển khai Serverless**
  * Tự động triển khai Lambda bằng CodeDeploy.
  * Kiểm thử các chiến lược rollout an toàn như **Linear** & **Canary**.

* **Bảo mật & Quản trị Pipeline**
  * Thêm bước phê duyệt, phân quyền IAM chi tiết cho từng stage.
  * Theo dõi pipeline bằng CloudWatch & SNS.
  * Cải thiện độ ổn định và an toàn của toàn bộ CI/CD workflow.
