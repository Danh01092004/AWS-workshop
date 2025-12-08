---
title: "Blog 1"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# AWS for Games: Jackbox Games Mở Ra Cơ Hội Mới Với Amazon GameLift Streams

**Bởi David Holladay – ngày 6 tháng 3 năm 2025**

*Tags: Amazon CloudFront, Amazon GameLift, Amazon SQS, Amazon S3, Giải pháp Khách hàng, Phát triển Game, Game, Messaging, Networking & Content Delivery, Storage, Industries*

## Giới Thiệu

Jackbox Games là studio trò chơi có trụ sở tại Chicago, nổi tiếng với các tựa game party như Quiplash, Fibbage, Drawful, Trivia Murder Party, và nhiều trò khác. Với hơn 50 trò chơi trong danh mục, Jackbox theo đuổi mục tiêu về "gaming dễ tiếp cận" — tức là người chơi có thể tham gia từ thiết bị bất kỳ mà họ có. Toàn bộ hạ tầng server của công ty được xây dựng trên Amazon Web Services.

Trước đây, người chơi thường sử dụng TV để hiển thị trò chơi và điện thoại làm điều khiển — một cách chơi đơn giản nhưng vẫn rất phổ biến. Gần đây, Jackbox quyết định hợp tác với Amazon GameLift Streams để mang trải nghiệm chơi không cần cài đặt, truy cập trực tiếp cho người chơi.

Amazon GameLift Streams là một tính năng trong GameLift, cho phép trò chơi được stream với độ trễ thấp, khung hình cao và quy mô toàn cầu — giúp studio như Jackbox mở rộng phạm vi tiếp cận mà không cần phụ thuộc vào console hoặc thiết bị mạnh.

## 1. Kiểm Soát Chi Phí Khi Mở Rộng

Việc đưa một trò chơi lên nền tảng streaming có thể rất tốn kém nếu làm riêng lẻ. Jackbox có danh mục rất lớn, nên họ cần một cách tối ưu hóa chi phí.

### 1.1 Tạo Nhóm Stream (Stream Group) Cho Tất Cả Trò Chơi

AWS đã hợp tác với Jackbox để gom 50 trò chơi vào một Stream Group duy nhất trong Amazon GameLift Streams. Nhờ vậy, họ có thể mở rộng quy mô cho toàn bộ danh mục cùng nhau thay vì từng trò riêng biệt.

### 1.2 Multi-tenancy & Giảm Chi Phí Tài Nguyên

Vì các trò Jackbox không yêu cầu GPU mạnh, một instance server có thể chạy nhiều trò chơi cùng lúc – tức là áp dụng mô hình đa ứng dụng (multi-tenancy) để tiết kiệm chi phí.

### 1.3 Sử Dụng Data Channel Để Chèn Quảng Cáo

Amazon GameLift Streams cung cấp tính năng Data Channel, cho phép chèn quảng cáo vào các khoảnh khắc hợp lý giữa các vòng chơi — giúp Jackbox duy trì mô hình miễn phí hoặc hỗ trợ doanh thu bằng quảng cáo.

## 2. Cải Thiện Quy Trình Cập Nhật Và Phát Hành

### 2.1 Mô Hình Party Pack Truyền Thống & Hạn Chế

Trước đây, Jackbox phát hành trò chơi theo Party Packs — mỗi gói gồm 5 trò. Khi muốn cập nhật một trò, họ phải cập nhật toàn bộ gói trên mọi nền tảng, gây phức tạp trong quản lý và triển khai.

### 2.2 Streaming Cho Phép Cập Nhật Riêng Lẻ, Linh Hoạt

Với GameLift Streams, Jackbox có thể cập nhật một trò duy nhất ở server mà không ảnh hưởng các trò khác, và không cần quan tâm đến các platform khác nhau. Điều này cũng cho phép người chơi chuyển từ trò này sang trò kia mượt mà, mà không cần đóng mở gói trò.

### 2.3 Tăng Tính Khả Khám Phá Trò Chơi (Discoverability)

Khi mọi trò đều có thể truy cập qua dịch vụ streaming, người chơi có nhiều cơ hội thử trò mới ngay — thay vì bị giới hạn trong các gói họ đã mua trước.

## 3. Hỗ Trợ & Tích Hợp Sâu Với AWS

### 3.1 Hỗ Trợ Kỹ Thuật Tích Hợp Vào Slack

Trong quá trình triển khai, AWS hỗ trợ Jackbox trực tiếp thông qua Slack của họ — giúp đội phát triển dễ dàng trao đổi, giải quyết sự cố nhanh chóng. CTO Jackbox cho biết trải nghiệm này khiến AWS giống như một phần của đội họ.

### 3.2 Sử Dụng Nhiều Dịch Vụ AWS Khác

Bên cạnh GameLift Streams, Jackbox dùng nhiều dịch vụ AWS để vận hành hệ thống:

- **Amazon EC2** cho xử lý backend, session management
- **Amazon S3** cho lưu trữ tài nguyên trò chơi và dữ liệu
- **Amazon SQS** cho quản lý hàng đợi
- **Amazon CloudFront** để phân phối nội dung nhanh và ổn định

Tất cả đều nằm trong hệ sinh thái AWS mà Jackbox đã sử dụng từ trước.

## 4. Định Hướng Tương Lai & Tầm Nhìn

Jackbox rất kỳ vọng vào việc tiếp cận người chơi mới qua thiết bị phổ biến như Smart TV, mà không yêu cầu console. Họ muốn trải nghiệm như mở ứng dụng streaming (như Netflix) để chơi trò chơi trực tiếp.

Streaming cũng tạo điều kiện để Jackbox xem xét hợp tác với các studio khác, đưa trò chơi từ các engine khác vào dịch vụ của họ — mở rộng danh mục nhanh hơn. CTO của Jackbox nhấn mạnh rằng streaming mở ra "mô hình kinh doanh mới" mà họ không làm được với cấu trúc Party Pack truyền thống — mô hình đăng ký, quảng cáo, truy cập trực tiếp — và GameLift Streams mang lại linh hoạt để họ tiếp tục phát triển.

## Kết Luận

Nhờ ứng dụng Amazon GameLift Streams, Jackbox Games đạt được nhiều lợi ích:

- Mở rộng khả năng tiếp cận người chơi toàn cầu
- Giảm chi phí vận hành nhờ multi-tenancy và quản lý tập trung
- Đơn giản hóa quy trình cập nhật trò chơi
- Cho phép mô hình doanh thu linh hoạt hơn (quảng cáo, đăng ký)
- Cải thiện trải nghiệm người chơi và khả năng khám phá nội dung

Sự hợp tác giữa Jackbox và AWS cho thấy streaming trò chơi không chỉ là xu hướng, mà là nền tảng để đổi mới trong ngành game.

## Về Tác Giả

**David Holladay**

David Holladay là Principal Solutions Architect thuộc nhóm AWS Game Tech, chuyên tư vấn và hỗ trợ các studio trò chơi trong việc xây dựng hạ tầng quy mô lớn trên AWS. Ông có hơn 15 năm kinh nghiệm trong phát triển phần mềm và thiết kế hệ thống cho ngành game, từng làm việc với nhiều studio hàng đầu thế giới. Khi không làm việc, David yêu thích việc stream các game indie mới ra mắt và tham gia các sự kiện game jam để chia sẻ kinh nghiệm lập trình với cộng đồng phát triển trò chơi.  
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
