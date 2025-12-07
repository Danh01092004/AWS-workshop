---
title: "Event 2"
date: 2025-01-01
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---


# Báo cáo tổng kết: “DevOps on AWS Workshop”

## Mục tiêu sự kiện

- Giới thiệu văn hoá, tư duy và các nguyên tắc DevOps  
- Trình bày hệ thống dịch vụ DevOps trên AWS phục vụ CI/CD  
- Thực hành Infrastructure as Code (IaC) với CloudFormation và CDK  
- Tìm hiểu containerization và orchestration trên AWS  
- Giới thiệu monitoring, observability và quy trình xử lý sự cố  
- Chia sẻ case study DevOps thực tế và định hướng nghề nghiệp

---

# Lịch trình & Nội dung chính của Workshop

### Buổi sáng (8:30 – 12:00)

---

### 8:30 – 9:00 AM | Welcome & DevOps Mindset

### Nội dung
- **Ôn lại nội dung buổi AI/ML** và mối liên hệ với DevOps  
- Giới thiệu **văn hoá DevOps**, tăng tính cộng tác và phản hồi liên tục  
- Các chỉ số DevOps quan trọng:  
  - **DORA metrics** (Lead Time, Deployment Frequency, Change Failure Rate, MTTR)  
  - Vai trò của minh bạch và cải tiến liên tục  

**Điểm nổi bật:**
- Nhấn mạnh DevOps là một **sự thay đổi văn hoá**, không chỉ là công nghệ  
- Làm rõ cách AI/ML được tích hợp vào quy trình DevOps  
- DevOps giúp tăng tốc độ phát triển, cải thiện độ ổn định và gắn kết tổ chức  

---

### 9:00 – 10:30 AM | AWS DevOps Services – CI/CD Pipeline

### Thành phần chính
- **Source Control** với AWS CodeCommit  
  - Chiến lược Git: **GitFlow**, **Trunk-based development**  
- **Build & Test** với CodeBuild  
  - Buildspec, unit test, integration test  
- **Triển khai** với CodeDeploy  
  - Các chiến lược: **Blue/Green**, **Canary**, **Rolling update**  
- **Orchestration** với CodePipeline  
  - Pipeline tự động hoá từ Source → Build → Test → Deploy

### Demo
- CI/CD toàn diện từ commit → build → deploy  
- Blue/Green deployment + rollback tự động  

**Kết luận chính:**
- CI/CD giúp giảm rủi ro triển khai và tăng ổn định  
- Các chiến lược triển khai giảm downtime đáng kể  
- CodePipeline tự động hoá quy trình với chi phí vận hành thấp  

---

### 10:30 – 10:45 AM | Nghỉ giải lao

---

### 10:45 AM – 12:00 PM | Infrastructure as Code (IaC)

### Nội dung chính
- **AWS CloudFormation**
  - Template, stack lifecycle, drift detection  
- **AWS CDK (Cloud Development Kit)**
  - Construct, pattern có thể tái sử dụng, hỗ trợ đa ngôn ngữ  
- **So sánh IaC**
  - CloudFormation (declarative) vs CDK (programmatic)

### Demo
- Deploy hạ tầng bằng **CloudFormation**  
- Deploy cùng kiến trúc bằng **AWS CDK**

**Thảo luận: Chọn công cụ IaC phù hợp**
- CloudFormation: chính xác, rõ ràng, ổn định  
- CDK: linh hoạt, nhanh, dễ tái sử dụng  

---

### 12:00 – 1:00 PM | Nghỉ trưa (tự túc)

---

# Buổi chiều (1:00 – 5:00 PM)

---

### 1:00 – 2:30 PM | Container Services on AWS

### Nội dung
- **Docker Fundamentals**
  - Microservices, Dockerfile, container lifecycle  
- **Amazon ECR**
  - Lưu trữ image, quét lỗ hổng, lifecycle policy  
- **Amazon ECS & EKS**
  - Quản lý cluster, scaling, orchestration  
  - So sánh ECS/Fargate và EKS  
- **AWS App Runner**
  - Triển khai container đơn giản hoá

### Demo & Case Study
- Deploy microservices trên **ECS**, **EKS** và **App Runner**  
- Phân tích ưu/nhược điểm: chi phí, độ phức tạp, trải nghiệm dev  

**Điểm nổi bật:**
- Khi nào nên chọn ECS, EKS hay App Runner  
- Vai trò của scanning & lifecycle trong quản lý image  
- Case study về chuyển đổi từ monolith sang microservices  

---

### 2:30 – 2:45 PM | Nghỉ giải lao

---

### 2:45 – 4:00 PM | Monitoring & Observability

### Nội dung
- **CloudWatch**
  - Metrics, Logs, Alarms, Dashboard, Anomaly Detection  
- **AWS X-Ray**
  - Distributed tracing, phân tích bottleneck  
- **Toàn bộ quy trình quan sát**
  - Collect → Analyze → Visualize → Alert

### Demo
- Tạo dashboard observability full-stack  
- Tracing request giữa các microservices bằng X-Ray  

**Best Practices**
- Giảm tình trạng “alert fatigue”  
- Dashboard dành cho DevOps/SRE  
- Structured logging, correlation IDs  

---

### 4:00 – 4:45 PM | DevOps Best Practices & Case Studies

### Nội dung
- Feature flags, A/B testing, progressive delivery  
- Automated testing trong CI/CD  
- Incident management & blameless postmortem  
- Case study: Startup & Enterprise chuyển đổi DevOps

**Điểm nổi bật:**
- Cách các đội hiệu suất cao vận hành ở quy mô lớn  
- Vì sao postmortem giúp cải tiến liên tục  
- Những bài học thực tế từ quá trình DevOps transformation  

---

### 4:45 – 5:00 PM | Q&A & Kết thúc

### Nội dung kết thúc
- Lộ trình nghề nghiệp DevOps  
- Lộ trình chứng chỉ AWS đề xuất  
- Thảo luận và networking cuối buổi  

---

# Key Takeaways

### Văn hoá DevOps
- Tập trung vào cộng tác – tự động hoá – cải tiến liên tục  
- DORA metrics giúp đo lường hiệu quả rõ ràng  

### Kỹ thuật
- CI/CD làm giảm rủi ro triển khai và tăng tốc độ  
- CloudFormation & CDK giúp chuẩn hoá hạ tầng  
- ECS/EKS/App Runner cung cấp lựa chọn linh hoạt cho container  
- Monitoring & observability là yếu tố sống còn để vận hành hệ thống phân tán  

### Ứng dụng vào công việc
- Áp dụng trunk-based để tăng tốc release  
- Tự động hoá testing và triển khai  
- Sử dụng IaC để tránh cấu hình sai lệch (drift)  
- Thiết lập dashboard quan sát và tracing toàn diện  

---

# Trải nghiệm sự kiện

### Học hỏi từ chuyên gia
- Chia sẻ thực tiễn tốt nhất về DevOps và hệ thống AWS  
- Case study giúp hiểu rõ cách triển khai trong thực tế  

### Trải nghiệm thực hành
- Demo CI/CD làm rõ từng giai đoạn của pipeline  
- IaC demo cho thấy sự khác biệt rõ ràng giữa CloudFormation và CDK  
- So sánh triển khai container giúp ra quyết định đúng đắn hơn  

### Kết nối & thảo luận
- Giao lưu với các kỹ sư, chuyên gia DevOps  
- Thảo luận về tự động hoá, scaling, quản lý sự cố  

### Bài học
- DevOps là sự kết hợp giữa văn hoá và công nghệ  
- Observability là nền tảng của vận hành ổn định  
- Chọn mô hình orchestrator phù hợp phụ thuộc vào đội ngũ và workload  

---

