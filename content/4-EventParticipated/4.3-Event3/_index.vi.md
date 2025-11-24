---
title: "Event 3"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 4.3. </b> "
---
# Báo cáo tóm tắt: “Hội thảo Security trên AWS”

## Mục tiêu sự kiện

- Implement MFA and IAM least privilege  
- Encrypt all critical data with KMS  
- Enable GuardDuty, CloudTrail, Config by default  
- Use multi-account architecture with Control Tower 
 

---

# Lịch trình & Điểm nhấn chính

# Buổi sáng (8:30 AM – 12:00 PM)

---

### 8:30 – 9:00 AM | Chào mừng & Tổng quan về An ninh

### Nội dung
- Ôn tập các buổi Cloud & DevOps trước  
- Giới thiệu **Mô hình Trách nhiệm Chung (Shared Responsibility Model)** của AWS  
- Xu hướng các mối đe dọa trên cloud và bối cảnh Việt Nam  

**Điểm nhấn:**
- Phân định rõ ràng trách nhiệm bảo mật giữa AWS và khách hàng  
- Nhấn mạnh các mối đe dọa phổ biến: phishing, misconfiguration, rò rỉ dữ liệu  
- Tầm quan trọng của tự động hóa và nguyên tắc Zero Trust  

---

### 9:00 – 10:30 AM | Quản lý Danh tính & Quyền truy cập (IAM)

### Thành phần chính
- Cấu trúc IAM: **Users**, **Roles**, **Groups**, **Policies**  
- Giới hạn quyền (Permission Boundaries) & Chính sách kiểm soát dịch vụ (SCPs)  
- IAM Identity Center cho quản lý tập trung  
- MFA, xoay vòng credential, và audit best practices  

### Demo
- Tạo và kiểm tra chính sách IAM  
- Áp dụng nguyên tắc **least privilege**  

**Điểm nhấn chính**
- Least-privilege giảm rủi ro khi bị xâm phạm  
- IAM Identity Center tối ưu cho môi trường đa tài khoản  
- SCP giúp quản trị ở cấp tổ chức  

---

### 10:30 – 10:45 AM | Coffee Break
- Chill 
- Tolet 
- Drink Coffe 

---

### 10:45 AM – 12:00 PM | Bảo mật mạng

### Nội dung
- Best practice thiết kế **VPC**  
- Public vs Private subnet, NAT, tách subnet  
- **Security Groups** vs **Network ACLs**  
- Tổng quan AWS WAF, Shield, Network Firewall  

### Bài tập
- Thiết kế kiến trúc VPC an toàn nhiều tầng  

**Thảo luận**
- Phòng thủ theo lớp (defense in depth)  
- Bảo vệ ứng dụng khỏi DDoS, OWASP Top 10  
- Kiểm tra mạng tập trung bằng AWS Network Firewall  

---

### 12:00 – 1:00 PM | Nghỉ trưa (Tự túc)

---

# Buổi chiều (1:00 PM – 5:00 PM)

---

### 1:00 – 2:30 PM | Bảo vệ dữ liệu & Mã hóa

### Nội dung
- **AWS KMS**: chính sách key, xoay vòng, envelope encryption  
- Mã hóa cho: **S3**, **EBS**, **RDS**, **DynamoDB**  
- Quản lý bí mật với **Secrets Manager**  
- Quản lý chứng chỉ với **ACM**  

### Demo
- Triển khai mã hóa ở quy mô lớn  
- Tự động xoay vòng secret  

**Điểm nhấn**
- Mã hóa phải thực hiện cả **lưu trữ** và **truyền tải**  
- Cấu hình key sai có thể gây lỗi hệ thống  
- Secrets Manager giảm rủi ro credential bị hardcode  

---

### 2:30 – 2:45 PM | Nghỉ giải lao

---

### 2:45 – 4:00 PM | Giám sát & Phản ứng sự cố

### Nội dung
- AWS Security Hub, GuardDuty, Config, CloudTrail, Detective  
- Phát hiện mối đe dọa & tuân thủ liên tục  
- Chu trình xử lý sự cố (incident response lifecycle)  

### Demo
- Xây dựng Dashboard Security Operations  
- Điều tra mối đe dọa với GuardDuty + Detective  

**Best Practices**
- Bật CloudTrail trên toàn tổ chức  
- Config Rules phát hiện misconfiguration  
- Tự động cảnh báo bằng SNS, EventBridge, Lambda  

---

### 4:00 – 4:30 PM | Tuân thủ & Quản trị

### Nội dung
- Các tiêu chuẩn quốc tế: **GDPR, HIPAA, PCI-DSS, SOC 2, ISO 27001**  
- AWS Control Tower & Organizations  
- Quản trị cho môi trường đa tài khoản  
- Case study: Mô hình bảo mật doanh nghiệp đa tài khoản  

**Điểm nhấn**
- Tuân thủ ≠ Bảo mật (cần cả hai)  
- Control Tower đảm bảo guardrails cho lifecycle account  
- Môi trường đa tài khoản tăng cường isolation & least privilege  

---

### 4:30 – 4:50 PM | AWS Well-Architected Security Pillar

### Nội dung
- Identity, Detection, Infrastructure, Data, Response  
- Tự động hóa bảo mật & DevSecOps  
- Kiến trúc Zero Trust  
- Tối ưu chi phí kiểm soát bảo mật  

**Điểm nhấn**
- Shift-left security trong CI/CD  
- Identity là nền tảng của Zero Trust  
- Tự động hóa giảm lỗi vận hành và tiếng ồn  

---

### 4:50 – 5:00 PM | Kết thúc & Tổng kết

### Nội dung
- Key takeaways từ AWS Cloud Mastery Series  
- Lộ trình học nâng cao và chứng chỉ  
- Networking & thảo luận nhóm  

---

# Những điểm rút ra chính

### Văn hóa bảo mật
- Shared Responsibility Model xác định rõ ràng trách nhiệm  
- Identity là tuyến phòng thủ đầu tiên  

### Kỹ năng kỹ thuật
- Quản trị IAM đảm bảo bảo mật mở rộng  
- KMS đơn giản hóa mã hóa dữ liệu  
- Isolation mạng giảm bề mặt tấn công  
- Security Hub + GuardDuty giúp giám sát liên tục  

### Áp dụng vào công việc
- Bật MFA & áp dụng least privilege cho IAM  
- Mã hóa tất cả dữ liệu quan trọng bằng KMS  
- Bật GuardDuty, CloudTrail, Config mặc định  
- Sử dụng multi-account architecture với Control Tower  

---

# Trải nghiệm sự kiện

### Học hỏi từ chuyên gia
- Ví dụ thực tế về các vụ tấn công trên cloud  
- Giải thích chi tiết các công cụ bảo mật AWS  
- Minh họa rõ ràng IAM & mã hóa  

### Thực hành
- Bài tập IAM & KMS  
- Thiết kế VPC bảo mật  
- Demo điều tra sự cố  

### Networking
- Trao đổi với các kỹ sư cloud & chuyên viên bảo mật  
- Thảo luận về compliance & scaling security  

### Bài học rút ra
- Misconfiguration là nguyên nhân số 1 gây sự cố  
- Bảo mật cần liên tục và tự động  
- Zero Trust là tiêu chuẩn mới  

---

### Hình ảnh sự kiện  
*Thêm ảnh minh họa hội thảo tại đây*

> Tổng quan, “Hội thảo Security trên AWS” cung cấp kiến thức thực tế và sâu sắc về bảo mật cloud, quản trị, giám sát mối đe dọa, giúp xây dựng kiến trúc AWS an toàn và tuân thủ.
