---
title: "Blog 1"
date: 2023-10-10
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Cách AWS Bảo Vệ Khách Hàng Trước Các Cuộc Tấn Công DDoS

## Tổng quan  
Từ cuối tháng 8/2023, AWS đã phát hiện và ngăn chặn một dạng tấn công DDoS mới: **HTTP/2 request flood**, cụ thể gọi là **HTTP/2 rapid reset attack**, nhắm vào Amazon CloudFront. Các đợt tấn công này gửi một lượng lớn yêu cầu kết nối HTTP/2 rồi ngay lập tức reset, làm quá tải máy chủ vì phải ghi log và phân tích yêu cầu trước khi bị hủy. ([aws.amazon.com](https://aws.amazon.com/blogs/security/how-aws-protects-customers-from-ddos-events/))

## Chi tiết sự kiện  
- Đỉnh điểm diễn ra vào **28–29/08/2023**, với lưu lượng đạt **hơn 155 triệu yêu cầu mỗi giây** qua CloudFront.  
- AWS quan sát và giảm thiểu nhiều sự kiện HTTP/2 rapid reset trong thời gian này, kéo dài đến tháng 9.  
- Các khách hàng xây dựng **kiến trúc chống DDoS** — dùng CloudFront, AWS Shield — đều duy trì được tính sẵn sàng trong suốt các cuộc tấn công.  

## Hiểu về HTTP/2 Rapid Reset Attack  
- HTTP/2 cho phép nhiều luồng logic trong một phiên, khác với HTTP/1.x.  
- Kẻ tấn công gửi nhiều yêu cầu rồi nhanh chóng reset mỗi luồng. Máy chủ vẫn phải tốn tài nguyên xử lý (phân tích, ghi log, …) dù không trả kết quả.  
- Đây là một dạng của HTTP request flood; quan trọng là phải phát hiện và hấp thụ lưu lượng độc hại trước khi đến hệ thống gốc.  

## Biện pháp phòng thủ & Thực hành tốt nhất của AWS  
- AWS cung cấp **bảo vệ DDoS tích hợp sẵn** trên hạ tầng.  
- Các dịch vụ khuyến nghị để tăng khả năng chống chịu:  
  - **Amazon CloudFront**  
  - **AWS Shield (bao gồm Shield Advanced)**  
  - **AWS WAF**  
  - **Amazon Route 53**  
  - **Route 53 Application Recovery Controller**  
- Các dịch vụ này giúp phân phối traffic qua edge toàn cầu, ngăn yêu cầu xấu đến máy chủ gốc.  
- Nên sử dụng **caching tại edge (CloudFront)**, **lọc traffic (WAF)**, và **định tuyến toàn cầu (Route 53)** để hấp thụ hoặc chặn tấn công.  

## Tình báo mối đe dọa, Giám sát & Hợp tác  
- AWS liên tục giám sát lưu lượng để phát hiện bất thường.  
- Kỹ sư AWS kết hợp tình báo mối đe dọa toàn cầu, dữ liệu giám sát và tự động hóa để đối phó với kỹ thuật DDoS mới.  
- AWS hợp tác với các đơn vị bên ngoài (CERTs, ISP, nhà đăng ký tên miền, các nhà cung cấp cloud khác) để truy vết, giảm thiểu, thậm chí gỡ bỏ nguồn gốc của các cuộc tấn công lớn.  

## Tóm tắt  
AWS đã phản ứng nhanh chóng trước dạng tấn công DDoS mới (HTTP/2 rapid reset) vào cuối tháng 8 và đầu tháng 9/2023. Nhờ các biện pháp bảo vệ tích hợp sẵn cùng kiến trúc tối ưu (CloudFront, Shield, WAF, Route 53), khách hàng vẫn duy trì được dịch vụ. Hoạt động giám sát, tình báo mối đe dọa, và giảm thiểu ở tầng hạ tầng là trọng tâm trong chiến lược bảo vệ khách hàng trước những mối đe dọa DDoS ngày càng phát triển.  
