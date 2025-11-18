---
title: "Worklog Tuần 3"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Học và thực hành với Amazon VPC (mạng cơ bản, subnet, bảng định tuyến, security groups).  
* Thực hành với EC2 instances: khởi tạo, kết nối bằng SSH, gắn thêm bộ nhớ.  
* Hiểu về EBS, Elastic IP và cấu hình Security Group.  
* Kết hợp AWS Console và CLI để quản lý mạng và lưu trữ của EC2.  

### Nhiệm vụ trong tuần:
| Ngày | Nhiệm vụ                                                                                                                                                                                                  | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | ---------------- | ----------------------------------------- |
| 2 | - Đọc qua các yêu cầu trong hướng dẫn lab <br> - Hiểu cơ sở hạ tầng toàn cầu của AWS (Regions, AZs, VPC) <br> - Ôn tập các khái niệm mạng cơ bản (subnet, bảng định tuyến, gateway) | 22/09/2025 | 22/09/2025 | <https://000003.awsstudygroup.com/vi/> |
| 3 | - Học cách tạo VPC tùy chỉnh <br>&emsp; + Xác định CIDR block <br>&emsp; + Thêm subnet công khai & riêng tư <br>&emsp; + Cấu hình bảng định tuyến & internet gateway <br>&emsp; + Gắn subnet | 23/09/2025 | 23/09/2025 | <https://000004.awsstudygroup.com/vi/> |
| 4 | - Khám phá mạng của EC2: <br>&emsp; + Security Groups (luồng vào & luồng ra) <br>&emsp; + Key pairs cho SSH <br> - Chuẩn bị môi trường để khởi tạo EC2 Linux instance | 24/09/2025 | 24/09/2025 | <https://000004.awsstudygroup.com/vi/> |
| 5 | - Thực hành khởi tạo EC2: <br>&emsp; + Chọn AMI (Amazon Linux/Ubuntu) <br>&emsp; + Chọn loại instance (t2.micro) <br>&emsp; + Cấu hình mạng (VPC, subnet, SG) <br>&emsp; + Gán Elastic IP <br> - Kiểm tra kết nối SSH | 25/09/2025 | 25/09/2025 | <https://000004.awsstudygroup.com/vi/> |
| 6 | - Làm việc với bộ nhớ: <br>&emsp; + Tạo và gắn thêm EBS volume <br>&emsp; + Định dạng và mount volume <br> - Kiểm tra trạng thái instance & kết nối qua Console & CLI <br> - Dọn dẹp tài nguyên (xóa EC2, giải phóng Elastic IP, xóa volume) | 26/09/2025 | 26/09/2025 | <https://000004.awsstudygroup.com/vi/> |

### Kết quả đạt được tuần 3:

* Hiểu cơ sở hạ tầng toàn cầu của AWS (Regions, AZs, và VPC).  
* Tạo thành công một VPC tùy chỉnh với subnet, bảng định tuyến và internet gateway.  
* Học cách cấu hình Security Groups và quản lý luồng vào/ra.  
* Khởi tạo thành công một Linux EC2 instance với cấu hình mạng phù hợp.  
* Thực hành kết nối EC2 bằng SSH với key pair.  
* Gán và kiểm tra Elastic IP để có địa chỉ công cộng ổn định.  
* Gắn, định dạng và mount một EBS volume để mở rộng bộ nhớ.  
* Kiểm tra trạng thái instance và tài nguyên bằng cả AWS Console và CLI.  
* Thực hành dọn dẹp tài nguyên đúng cách: xóa EC2, giải phóng Elastic IP, xóa EBS volume.  
* Xây dựng nền tảng vững chắc về AWS networking (VPC) và compute (EC2).  
