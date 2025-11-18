---
title: "Bản đề xuất"
date: 2025-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---



# Mini Food Social  
## Nền tảng mạng xã hội ẩm thực serverless tích hợp AI sinh công thức món ăn

### 1. Tóm tắt điều hành (Executive Summary)
**Mini Food Social** là một dự án web serverless hiện đại, được thiết kế cho cộng đồng yêu thích ẩm thực.  
Người dùng có thể đăng bài chia sẻ món ăn, tải ảnh món ăn, bình luận, thả tim, và đặc biệt — sử dụng **AI (Amazon Bedrock)** để gợi ý **công thức nấu ăn mới** dựa trên nội dung bài viết hoặc hình ảnh.  

Hệ thống hỗ trợ tối đa **100 người dùng đã đăng ký**, cung cấp tính năng **đăng nhập bảo mật**, **CRUD bài viết**, **bình luận và like**, hoạt động hoàn toàn dựa trên kiến trúc **AWS Serverless**, giúp tiết kiệm chi phí và dễ mở rộng.

**Các dịch vụ AWS sử dụng**
- **AWS Amplify**: Lưu trữ và CI/CD cho web app (Next.js).  
- **Amazon API Gateway**: Giao tiếp giữa frontend và backend.  
- **AWS Lambda**: Xử lý logic nghiệp vụ và API.  
- **Amazon DynamoDB**: Lưu trữ bài viết, người dùng, bình luận, lượt thích.  
- **Amazon Cognito**: Quản lý xác thực người dùng (đăng ký/đăng nhập).  
- **Amazon Bedrock (Claude Model)**: Tạo công thức món ăn bằng AI.  
- **Amazon CloudFront + WAF + Route 53**: Phân phối nội dung nhanh và bảo mật.  

**Chi phí ước tính:** khoảng **$16.70/tháng** (~**$200.40/năm**) nếu không sử dụng free tier.

---

### 2. Xác định vấn đề
### Vấn đề hiện tại
Các nền tảng chia sẻ công thức món ăn hiện nay thường:
- Không có tính năng gợi ý công thức bằng AI.  
- Cần nhiều tài nguyên để vận hành backend.  
- Thiếu bảo mật và không tối ưu chi phí khi mở rộng.  

Việc duy trì máy chủ truyền thống cho các tính năng mạng xã hội như bài viết, bình luận và AI rất tốn công sức và chi phí.

### Giải pháp
Mini Food Social giải quyết vấn đề này bằng **kiến trúc AWS serverless hoàn toàn**:
- **Amplify + Next.js**: Triển khai và lưu trữ frontend.  
- **Cognito**: Quản lý đăng nhập, xác thực và token JWT.  
- **API Gateway + Lambda**: Xử lý yêu cầu CRUD và gọi AI.  
- **DynamoDB**: Lưu bài viết, bình luận, người dùng.  
- **Bedrock (Claude)**: Sinh công thức món ăn từ prompt hoặc ảnh.  
- **CloudFront + WAF**: Bảo vệ và tăng tốc tải trang toàn cầu.  

### Lợi ích & Hiệu quả đầu tư
- **Chi phí thấp:** Chỉ trả khi có người dùng.  
- **Không cần máy chủ:** Tự động mở rộng, bảo trì tối thiểu.  
- **AI thông minh:** Gợi ý công thức sáng tạo, tăng tương tác.  
- **Bảo mật:** Cognito xác thực và dữ liệu mã hóa an toàn.  

Giải pháp chứng minh khả năng xây dựng mạng xã hội nhỏ gọn, có AI tích hợp, với chi phí thấp hơn 500.000 VNĐ/tháng.

---

### 3. Kiến trúc giải pháp
Mini Food Social sử dụng **kiến trúc 5 lớp**, giúp tách biệt rõ ràng và dễ mở rộng:

1. **Frontend (Amplify + Next.js)**  
   - Cho phép người dùng đăng bài, tải ảnh, xem bài viết.  
   - Gọi API thông qua Cognito token.  

2. **API Gateway + Lambda Router**  
   - Xử lý các API: đăng bài, xem bài, thả tim, gợi ý công thức.  

3. **Database (DynamoDB)**  
   - Lưu trữ bài viết, người dùng, lượt thích, kết quả AI.  

4. **AI Integration (Bedrock)**  
   - Sử dụng mô hình Claude để tạo công thức dựa trên ảnh hoặc mô tả món ăn.  

5. **Security & Delivery (CloudFront + WAF + Route 53)**  
   - Tăng tốc tải web và bảo vệ khỏi tấn công DDoS.  

**Sơ đồ kiến trúc**
<img src="/images/2-Proposal/Untitled Diagram.drawio.png" alt="Your profile picture" width="800" height="500" />

---

### 4. Triển khai kỹ thuật
**Các giai đoạn triển khai**

- **Giai đoạn 1 – Nghiên cứu & Thiết kế (Tháng 0)**  
  - Xác định yêu cầu hệ thống, vẽ sơ đồ kiến trúc AWS.  
  - Tìm hiểu Bedrock và cơ chế AI text generation.  

- **Giai đoạn 2 – Ước tính chi phí & Thiết lập môi trường (Tháng 1)**  
  - Sử dụng AWS Pricing Calculator để tính chi phí.  
  - Cấu hình Amplify, Cognito và GitLab CI/CD.  

- **Giai đoạn 3 – Phát triển & Tích hợp (Tháng 2)**  
  - Viết các Lambda API cho CRUD bài viết và AI recipe.  
  - Tạo DynamoDB tables và cấu hình quyền truy cập Cognito.  

- **Giai đoạn 4 – Triển khai & Kiểm thử (Tháng 3)**  
  - Triển khai Amplify, Lambda, API Gateway.  
  - Kiểm thử AI, API và xác thực người dùng.  

**Yêu cầu kỹ thuật**
- **Frontend:** Next.js + Amplify (SSR hosting).  
- **Backend:** Lambda + API Gateway + DynamoDB.  
- **AI Module:** Lambda gọi Bedrock (Claude) để sinh công thức.  
- **Auth:** Cognito (JWT token).  
- **Lưu trữ:** DynamoDB + S3 (cho ảnh upload).  

---

### 5. Lộ trình & Mốc thời gian
| Giai đoạn | Thời gian | Mô tả |
|------------|------------|-------|
| Tháng 0 | 1 tháng | Thiết kế kiến trúc hệ thống |
| Tháng 1 | 1 tháng | Thiết lập Amplify & Cognito, tính chi phí |
| Tháng 2 | 1 tháng | Phát triển Lambda API & tích hợp Bedrock |
| Tháng 3 | 1 tháng | Kiểm thử và triển khai chính thức |
| Sau triển khai | Liên tục | Thu thập phản hồi và tối ưu AI |

---

### 6. Ước tính chi phí
Xem chi tiết tại [AWS Pricing Calculator](https://calculator.aws/#/estimate?id=abcd1234efgh5678)  
Hoặc tải tệp: [Budget Estimation File](../attachments/budget_estimation_mfs.pdf)

#### Chi phí hạ tầng
| Dịch vụ | Ước tính/tháng | Ghi chú |
|----------|----------------|---------|
| AWS Amplify | $3.00 | Lưu trữ web app & CI/CD |
| API Gateway | $2.50 | 20,000 request/tháng |
| AWS Lambda | $2.00 | 50,000 lần gọi |
| DynamoDB | $1.20 | 1 GB dữ liệu |
| Cognito | $1.00 | 100 người dùng |
| Bedrock (Claude) | $5.00 | 500 lượt sinh công thức |
| CloudFront + WAF | $2.00 | CDN & bảo mật cơ bản |

**Tổng cộng:** ~$16.70/tháng (~$200.40/năm)

---

### 7. Đánh giá rủi ro
#### Ma trận rủi ro
| Rủi ro | Mức ảnh hưởng | Xác suất | Biện pháp |
|--------|----------------|----------|------------|
| Chi phí Bedrock tăng cao | Trung bình | Trung bình | Giới hạn số lần gọi AI/ngày |
| Tắc nghẽn API Gateway | Trung bình | Thấp | Sử dụng cache & CloudFront |
| Nóng phân vùng DynamoDB | Trung bình | Thấp | Thiết kế key hợp lý |
| Lỗi xác thực Cognito | Trung bình | Thấp | Refresh token tự động, backup đa vùng |
| Quá tải sử dụng | Thấp | Trung bình | Giới hạn request và cảnh báo chi phí |

#### Kế hoạch dự phòng
- Dùng công thức mẫu nếu Bedrock bị lỗi.  
- Chuyển DynamoDB sang chế độ on-demand khi lưu lượng tăng.  
- Cấu hình AWS Cost Alerts để cảnh báo vượt ngưỡng ngân sách.

---

### 8. Kết quả mong đợi
#### Cải tiến kỹ thuật
- Hệ thống **serverless** linh hoạt, tự động mở rộng.  
- **AI tích hợp** giúp tăng trải nghiệm và tính sáng tạo người dùng.  
- Giảm chi phí bảo trì và quản lý máy chủ.  

#### Giá trị dài hạn
- Minh chứng cho mô hình ứng dụng AI + Serverless trong thực tế.  
- Có thể mở rộng cho các nền tảng xã hội, học thuật, hoặc startup khác.  
- Là nền tảng thử nghiệm cho **AI recommendation system** trong tương lai.
