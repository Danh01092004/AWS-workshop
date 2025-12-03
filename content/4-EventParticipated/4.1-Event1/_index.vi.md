---
title: "Event 1"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---




# Summary Report: “AWS AI/ML & Generative AI Workshop”

### Event Objectives

- Giới thiệu hệ sinh thái AI/ML của AWS  
- Trình bày các dịch vụ cốt lõi như Amazon SageMaker và Amazon Bedrock  
- Hướng dẫn quy trình xây dựng & triển khai mô hình ML end-to-end  
- Giới thiệu Generative AI, Prompt Engineering và kiến trúc RAG  
- Hỗ trợ học viên thực hành qua demo và trao đổi trực tiếp cùng chuyên gia

---

# Workshop Agenda & Key Highlights

## 8:30 – 9:00 AM | Welcome & Introduction

### Hoạt động chính
- **Đăng ký & networking** với các chuyên gia và người tham dự  
- **Giới thiệu tổng quan workshop**, mục tiêu học tập  
- **Hoạt động ice-breaker** để kết nối nhóm  
- **Tổng quan về landscape AI/ML tại Việt Nam**: nhu cầu doanh nghiệp, xu hướng GenAI, các thách thức hiện tại

**Điểm nổi bật:**
- Người tham dự có cái nhìn tổng thể về sự phát triển của AI/ML trong nước  
- Nhấn mạnh vai trò của AWS trong việc hỗ trợ doanh nghiệp ứng dụng AI/ML một cách hiệu quả và an toàn

---

## 9:00 – 10:30 AM | AWS AI/ML Services Overview

### 1. Amazon SageMaker – End-to-End ML Platform
Các nội dung được trình bày:
- **Data preparation & labeling** với SageMaker Ground Truth  
- **Model training**, hyperparameter tuning  
- **Model deployment** qua SageMaker Endpoints  
- **MLOps tích hợp**: pipelines, model registry, CI/CD cho ML  

### 2. Live Demo: SageMaker Studio
- Trải nghiệm giao diện **SageMaker Studio**  
- Thực hành quy trình từ dữ liệu → training → inference  
- Minh họa auto-scaling endpoint và quản lý phiên bản mô hình  

**Key takeaways:**
- SageMaker cung cấp **một nền tảng duy nhất** cho toàn bộ vòng đời ML  
- Tiết kiệm thời gian vận hành & tăng tốc độ đưa mô hình vào production  
- Dễ dàng tích hợp với hệ sinh thái AWS (S3, Lambda, API Gateway…)

---

## 10:30 – 10:45 AM | Coffee Break
Thời gian để nghỉ ngơi, trao đổi thêm với chuyên gia và thảo luận về các case thực tế.

---

## 10:45 AM – 12:00 PM | Generative AI with Amazon Bedrock

### 1. Foundation Models (FMs)
So sánh và hướng dẫn lựa chọn:
- **Claude** – reasoning mạnh, an toàn, phù hợp enterprise  
- **Llama** – mã nguồn mở, tuỳ chỉnh linh hoạt  
- **Titan** – tối ưu cho doanh nghiệp với tích hợp chặt chẽ AWS  

### 2. Prompt Engineering
- Kỹ thuật **prompting**, **Chain-of-Thought**, **few-shot**  
- Chiến lược nâng cao độ chính xác và kiểm soát đầu ra  
- Demo prompt với nhiều mô hình trên Bedrock

### 3. Retrieval-Augmented Generation (RAG)
- Giải thích kiến trúc RAG  
- Cách tạo **Knowledge Base** trong Amazon Bedrock  
- Cách mô hình truy xuất dữ liệu riêng của doanh nghiệp để trả lời chính xác  
- Best practices: chunking, embedding model selection, vector store

### 4. Bedrock Agents
- Xây dựng **multi-step workflows**, tích hợp công cụ (tool integration)  
- Use cases: customer support bots, enterprise assistant, data automation

### 5. Guardrails
- Thiết lập **safety**, chặn nội dung không phù hợp  
- Điều chỉnh **content filtering** theo nhu cầu doanh nghiệp  
- Đảm bảo mô hình tuân thủ quy định bảo mật & kiểm soát dữ liệu

---

# Key Takeaways

### Tư duy thiết kế hệ thống AI
- Chọn **đúng mô hình** cho use case: reasoning, text generation, code, search  
- Xây dựng hệ thống **có giám sát**, có guardrails, theo chuẩn bảo mật AWS  
- MLOps và GenAIOps giúp quy trình ML/GenAI ổn định và dễ mở rộng

### Kiến thức kỹ thuật
- SageMaker hỗ trợ end-to-end ML từ data → model → deployment  
- Bedrock giúp build ứng dụng GenAI **không cần tự huấn luyện mô hình lớn**  
- RAG giải quyết bài toán kiến thức riêng tư cho doanh nghiệp  
- Prompt Engineering đóng vai trò quan trọng trong chất lượng đầu ra

### Chiến lược ứng dụng vào công việc
- Bắt đầu với **pilot nhỏ**, dùng Bedrock để thử nghiệm nhanh  
- Xây dựng **PoC RAG** cho hệ thống tra cứu tài liệu nội bộ  
- Tích hợp SageMaker vào pipeline hiện tại để tự động hóa ML  
- Thử nghiệm **Bedrock Agents** để tối ưu quy trình kinh doanh

---

# Event Experience

### Học hỏi từ chuyên gia
- Các speaker cung cấp insight sâu về AI/ML, từ kỹ thuật đến ứng dụng thực tế  
- Những case study của doanh nghiệp Việt Nam giúp hiểu rõ cách triển khai thực tiễn  

### Trải nghiệm thực hành
- Demo SageMaker Studio giúp hình dung rõ ràng pipeline end-to-end  
- Tìm hiểu cách build ứng dụng GenAI trên Bedrock nhanh và an toàn  

### Kết nối & thảo luận
- Networking giúp mở rộng góc nhìn và cách các team khác áp dụng AI  
- Thảo luận về vấn đề dữ liệu, chi phí và bảo mật khi triển khai ML/GenAI  

### Bài học rút ra
- AI/ML cần được áp dụng theo **chiến lược rõ ràng**, không chạy theo trend  
- RAG và Guardrails là yếu tố bắt buộc khi đưa GenAI vào môi trường enterprise  
- SageMaker và Bedrock giúp doanh nghiệp tiết kiệm thời gian, giảm chi phí và tăng tốc đổi mới

---

#### Một số hình ảnh tại sự kiện
<img src="/images/5-Workshop/Event-1.jpg" alt="Your profile picture" width="800" height="500" />


