---
title: "Worklog Tuần 8"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---



### Mục tiêu Tuần 8:

* Học các khái niệm nâng cao về **AWS Networking** gồm **VPC Peering**, **Transit Gateway** và **PrivateLink**.  
* Triển khai **kết nối hybrid cloud** giữa hệ thống on-premises và AWS.  
* Hiểu và cấu hình **AWS Direct Connect** cho kết nối mạng chuyên dụng.  
* Thực hành **bảo mật mạng** và **quản lý luồng truy cập** hiệu quả.  
* Giám sát và xử lý sự cố mạng bằng **VPC Flow Logs** và **Amazon CloudWatch**.  

---

### Nhiệm vụ thực hiện trong tuần:

| Ngày | Nhiệm vụ | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | ---- | ----------- | ---------------- | ------------------ |
| 2 | - Nghiên cứu khái niệm **VPC Peering** và **Transit Gateway**. <br> - **Thực hành:** <br>&emsp; + Tạo kết nối VPC Peering giữa hai VPC. <br>&emsp; + Cấu hình bảng định tuyến (Routing Table) để điều hướng lưu lượng. <br>&emsp; + Kiểm tra khả năng kết nối giữa các EC2 instance. <br><br> → Hiểu cách giao tiếp giữa các VPC. | 27/10/2025 | 27/10/2025 | AWS Study Group |
| 3 | - Tìm hiểu về **AWS PrivateLink** và dịch vụ endpoint. <br> - **Thực hành:** <br>&emsp; + Tạo endpoint PrivateLink để truy cập dịch vụ nội bộ. <br>&emsp; + Kiểm tra khả năng truy cập dịch vụ mà không sử dụng Internet công cộng. <br><br> → Đảm bảo kết nối riêng tư và bảo mật. | 28/10/2025 | 28/10/2025 | AWS Study Group |
| 4 | - Khám phá **AWS Direct Connect** cho kết nối mạng chuyên dụng. <br> - **Thực hành:** <br>&emsp; + Tạo kết nối Direct Connect. <br>&emsp; + Thiết lập Virtual Interface (VIF) và xác minh định tuyến. <br><br> → Giảm độ trễ và cải thiện độ tin cậy băng thông. | 29/10/2025 | 29/10/2025 | AWS Study Group |
| 5 | - Tìm hiểu về **thiết kế hybrid cloud** và tích hợp với hệ thống on-premises. <br> - **Thực hành:** <br>&emsp; + Kết nối mạng nội bộ (on-premises) với AWS qua VPN và Direct Connect. <br>&emsp; + Kiểm tra failover và định tuyến giữa tài nguyên cục bộ và cloud. <br><br> → Có kinh nghiệm thực hành về mạng hybrid. | 30/10/2025 | 30/10/2025 | AWS Study Group |
| 6 | - Thực hiện **giám sát và bảo mật mạng**. <br> - **Thực hành:** <br>&emsp; + Kích hoạt **VPC Flow Logs** và phân tích lưu lượng. <br>&emsp; + Cấu hình **CloudWatch Alarms** cho các bất thường mạng. <br>&emsp; + Áp dụng **Security Group** và **Network ACL** theo best practices. <br><br> → Đảm bảo môi trường mạng an toàn và có khả năng giám sát. | 31/10/2025 | 31/10/2025 | AWS Study Group |

---

### Kết quả đạt được trong Tuần 8:

* **VPC Peering & Transit Gateway**  
  - Thiết lập thành công các kết nối VPC Peering và kiểm tra luồng giao tiếp giữa các VPC.  
  - Cấu hình Transit Gateway để tập trung định tuyến giữa nhiều VPC.  

* **AWS PrivateLink**  
  - Tạo endpoint PrivateLink cho phép truy cập dịch vụ AWS một cách riêng tư và bảo mật.  
  - Xác minh lưu lượng không đi qua Internet công cộng, đảm bảo tính an toàn cao.  

* **AWS Direct Connect**  
  - Cấu hình kết nối mạng chuyên dụng thông qua Direct Connect.  
  - Kiểm tra định tuyến và cải thiện hiệu suất kết nối giữa on-premises và AWS.  

* **Tích hợp Hybrid Cloud**  
  - Kết nối mạng nội bộ với AWS bằng VPN và Direct Connect.  
  - Kiểm tra tính sẵn sàng, định tuyến và khả năng chuyển đổi (failover) giữa hai môi trường.  

* **Giám sát & Bảo mật Mạng**  
  - Kích hoạt VPC Flow Logs để theo dõi luồng lưu lượng mạng.  
  - Thiết lập CloudWatch Alarms để phát hiện bất thường.  
  - Áp dụng các cấu hình bảo mật tốt nhất với Security Group và NACL.  
