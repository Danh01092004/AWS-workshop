---
title: "Event 3"
date: 2025-11-29
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---



# Báo cáo tổng kết: “Hội Thảo AWS Well-Architected Security Pillar”

## Mục Tiêu Hội Thảo

Tham gia khóa học về 5 trụ cột bảo mật trong AWS Well-Architected Framework, giúp xây dựng nền tảng bảo mật vững chắc và quy trình ứng phó sự cố toàn diện.

---

## Nội Dung Chính

### Phần Mở Đầu (8:30 - 8:50 AM)

**Nền Tảng Bảo Mật**
- Vai trò của Security Pillar trong Well-Architected Framework
- Nguyên tắc cốt lõi: Least Privilege, Zero Trust, Defense in Depth
- Mô hình Trách nhiệm Chung (AWS Shared Responsibility Model)
- Các mối đe dọa hàng đầu trong môi trường cloud tại Việt Nam

---

### Trụ Cột 1: Quản Lý Nhận Dạng & Truy Cập (8:50 - 9:30 AM)

**Các Chủ Đề Chính**
- Kiến trúc IAM hiện đại: Users, Roles, Policies
- Tránh sử dụng long-term credentials
- IAM Identity Center: SSO và permission sets
- SCP (Service Control Policies) và permission boundaries cho multi-account
- MFA enforcement, credential rotation, Access Analyzer

**Demo Thực Hành**
- Xác thực IAM Policy
- Mô phỏng quyền truy cập

**Những Điểm Chính**
- Least privilege access giảm thiểu phạm vi ảnh hưởng
- IAM Identity Center tối ưu hóa bảo mật môi trường multi-account
- SCPs thực thi quản trị ở cấp tổ chức

---

### Trụ Cột 2: Phát Hiện (9:30 - 9:55 AM)

**Các Chủ Đề Chính**
- CloudTrail (ở cấp tổ chức), GuardDuty, Security Hub
- Logging tại mọi tầng: VPC Flow Logs, ALB logs, S3 logs
- Alerting và automation với EventBridge
- Detection-as-Code (infrastructure + rules)

**Các Thực Hành Tốt Nhất**
- Bật CloudTrail ở cấp tổ chức
- Sử dụng Config Rules để phát hiện cấu hình sai
- Tự động hóa cảnh báo với SNS, EventBridge, Lambda

---

### Giải Lao (9:55 - 10:10 AM)

---

### Trụ Cột 3: Bảo Vệ Cơ Sở Hạ Tầng (10:10 - 10:40 AM)

**Các Chủ Đề Chính**
- VPC segmentation: public vs private placement
- Security Groups vs NACLs: mô hình áp dụng thực tế
- WAF, Shield, Network Firewall
- Bảo vệ workload: EC2, ECS/EKS security basics

**Thực Hành Thiết Kế**
- Thiết kế kiến trúc VPC multi-tier an toàn

**Những Điểm Chính**
- Defense in depth: bảo vệ phòng thủ theo tầng
- Bảo vệ ứng dụng chống DDoS, OWASP Top 10
- Kiểm tra tập trung bằng AWS Network Firewall

---

### Trụ Cột 4: Bảo Vệ Dữ Liệu (10:40 - 11:10 AM)

**Các Chủ Đề Chính**
- AWS KMS: key policies, grants, rotation
- Mã hóa at-rest và in-transit: S3, EBS, RDS, DynamoDB
- Secrets Manager và Parameter Store: mô hình rotation
- Data classification và access guardrails

**Demo Thực Hành**
- Triển khai mã hóa quy mô lớn
- Tự động hóa secret rotation

**Những Điểm Chính**
- Mã hóa phải áp dụng cả at-rest và in-transit
- Cấu hình key policy không đúng có thể gây outage
- Secrets Manager giảm rủi ro từ hardcoded credentials

---

### Trụ Cột 5: Ứng Phó Sự Cố (11:10 - 11:40 AM)

**Các Chủ Đề Chính**
- IR lifecycle theo AWS
- Playbook cho các tình huống:
  - IAM key bị xâm phạm
  - S3 public exposure
  - EC2 malware detection
- Snapshot, isolation, evidence collection
- Auto-response bằng Lambda/Step Functions

**Những Điểm Chính**
- Xây dựng quy trình ứng phó sự cố toàn diện
- Tự động hóa phản ứng giảm thời gian xử lý
- Bảo tồn bằng chứng cho việc điều tra

---

### Tổng Kết & Hỏi Đáp (11:40 AM - 12:00 PM)

**Nội Dung Tổng Kết**
- Tổng kết 5 trụ cột của Security Pillar
- Common pitfalls trong thực tế doanh nghiệp Việt Nam
- Roadmap học tập: Security Specialty, SA Pro dựa trên nội dung này

---

## Những Điểm Chính Cần Nhớ

### Nền Tảng Bảo Mật
- Mô hình Trách nhiệm Chung xác định ranh giới bảo mật rõ ràng
- Identity là tuyến phòng thủ đầu tiên và mạnh nhất
- Kiến trúc Zero Trust trở thành tiêu chuẩn mới

### Kỹ Năng Kỹ Thuật
- IAM governance đảm bảo khả năng mở rộng bảo mật
- KMS đơn giản hóa mã hóa trên các dịch vụ AWS
- Isolation mạng giảm bề mặt tấn công
- Security Hub + GuardDuty = continuous monitoring

### Áp Dụng Vào Công Việc
- Triển khai MFA và IAM least privilege
- Mã hóa tất cả dữ liệu quan trọng với KMS
- Bật GuardDuty, CloudTrail, Config by default
- Sử dụng multi-account architecture với Control Tower
- Shift-left security trong CI/CD pipeline

---

## Kinh Nghiệm Thực Tế

### Kiến Thức Chuyên Gia
- Ví dụ thực tế về cloud breaches
- Deep dive vào AWS security controls
- Giải thích rõ ràng các khái niệm IAM và encryption

### Thách Thức Phổ Biến
- Misconfiguration là nguyên nhân #1 gây cloud incidents
- Bảo mật phải liên tục và tự động hóa
- Multi-account là essential cho isolation và least privilege

### Bài Học Rút Ra
- Compliance không bằng Security (cần cả hai)
- Automation giảm operational noise và mistakes
- Identity là nền tảng của Zero Trust

---

