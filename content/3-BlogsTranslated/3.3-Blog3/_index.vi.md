---
title: "Blog 3"
date: 2025-01-01
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# Amazon Inspector Suppression Rules: Thực hành tốt nhất cho AWS Organizations


## Thiết lập Delegated Administrator

Chỉ định một tài khoản AWS làm **delegated administrator** cho Amazon Inspector. Tài khoản này có thể quản lý tập trung các scans, tổng hợp findings và áp dụng suppression rules trên tất cả các tài khoản trong AWS Organization. Lợi ích bao gồm:

- Tầm nhìn tập trung về các lỗ hổng  
- Thực thi chính sách nhất quán  
- Giảm overhead quản trị  

**Các bước:**

1. Kích hoạt AWS Organizations và thêm các tài khoản thành viên.  
2. Gán vai trò delegated admin cho Amazon Inspector.  
3. Xác nhận quyền truy cập và phân quyền trên các tài khoản.



## Suppression Rules ở quy mô lớn

Suppression rules giúp lọc tự động các findings rủi ro thấp, cho phép nhóm bảo mật tập trung vào các lỗ hổng quan trọng. Điểm chính:

- Rules có thể dựa trên **thuộc tính của finding**, **tags tài nguyên** hoặc **CVSS scores**.  
- Findings bị suppression được **lưu trữ (archived)**, không bị xóa, đảm bảo khả năng kiểm toán.  
- Rules có thể áp dụng trên **nhiều tài khoản** thông qua delegated admin.  

**Ví dụ:** Suppress các findings cho EC2 instance không production, tag `Environment:Dev`, với CVSS thấp (<4).



## Tagging và Ưu tiên theo rủi ro

Sử dụng tags nhất quán trên các tài nguyên giúp nhóm ưu tiên lỗ hổng theo tác động kinh doanh:

- Tag theo **môi trường** (`Prod`, `Dev`, `Test`)  
- Tag theo **chủ sở hữu ứng dụng**  
- Tag theo **yêu cầu compliance**  

Amazon Inspector có thể dùng các tags này để tạo báo cáo và áp dụng suppression một cách có chọn lọc, phù hợp với ưu tiên của doanh nghiệp.



## Đánh giá liên tục và cải tiến

Suppression rules và cấu hình scan không phải là “thiết lập một lần rồi quên”. Giám sát liên tục đảm bảo hiệu quả:

1. Xem lại các findings đã suppression thường xuyên để đảm bảo rules vẫn hợp lệ.  
2. Điều chỉnh lịch scan, phạm vi và cài đặt để phù hợp với các dịch vụ hoặc workloads mới.  
3. Sử dụng báo cáo tổng hợp từ tài khoản delegated admin để xác định xu hướng và lỗ hổng.

Lợi ích:

- Duy trì compliance với các tiêu chuẩn bảo mật  
- Giảm “alert fatigue” cho nhóm bảo mật  
- Đảm bảo remediation kịp thời các lỗ hổng quan trọng


## Xem xét đa tài khoản

Quản lý suppression rules trên nhiều tài khoản AWS cần lập kế hoạch cẩn thận:

- Sử dụng **AWS Organizations** với delegated admin để tránh trùng lặp rules.  
- Áp dụng **mẫu kế thừa (inheritance patterns)** cho các tài khoản thành viên.  
- Kết hợp chiến lược tagging với suppression rules để target cụ thể các tài khoản hoặc workloads.  

Cách tiếp cận này đảm bảo **chính sách bảo mật nhất quán**, đồng thời cho phép mở rộng và linh hoạt cho tổ chức đang phát triển.

## Kết luận

Bằng cách tận dụng **delegated admin, suppression rules, tagging và đánh giá liên tục**, các tổ chức có thể quản lý lỗ hổng hiệu quả ở quy mô lớn bằng Amazon Inspector. Thực hành tốt nhất này đảm bảo nhóm bảo mật tập trung vào các vấn đề quan trọng trong khi vẫn duy trì khả năng kiểm toán và compliance trên tất cả tài khoản AWS.
