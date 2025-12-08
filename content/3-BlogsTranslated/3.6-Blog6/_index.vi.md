---
title: "Blog 6"
date: 2025-01-01
weight: 6
chapter: false
pre: " <b> 3.6. </b> "
---

# AWS for Database : Native SQL Server Replication Options on Amazon RDS Custom for SQL Server  
*(AWS Database, Amazon RDS Custom, SQL Server, Replication, Data & Analytics, Industries)*

## Introduction
Các ứng dụng hiện đại thường yêu cầu khả năng phân phối dữ liệu đáng tin cậy và tính sẵn sàng cao trên nhiều cơ sở dữ liệu để hỗ trợ hoạt động kinh doanh quan trọng. SQL Server Replication cho phép quản trị viên cơ sở dữ liệu (DBA) tự động phân phối dữ liệu giữa các cơ sở dữ liệu theo thời gian gần như thực, giúp giảm tải các tác vụ đọc nặng từ hệ thống sản xuất và đồng bộ dữ liệu giữa các vùng hoặc các môi trường cơ sở dữ liệu khác nhau.

Amazon RDS Custom for SQL Server là dịch vụ được quản lý kết hợp giữa sự linh hoạt của cơ sở dữ liệu tự quản và các lợi ích tự động hóa của một dịch vụ hoàn toàn được quản lý. Với RDS Custom, bạn có thể tận dụng các tính năng replication gốc của SQL Server trong khi AWS xử lý các tác vụ hạ tầng như backup, vá lỗi, snapshot và giám sát.  
Blog này khám phá cách cấu hình SQL Server Replication trên RDS Custom, bao gồm các loại replication được hỗ trợ (snapshot, transactional, merge, peer-to-peer) và hướng dẫn từng bước để cấu hình distributor, publication và subscription.  
Amazon Web Services, Inc.

---

## 1. Supported Replication Types & Comparison Table

#### 1.1 Roles & Capabilities of RDS Custom

| Role / Replication Mode | RDS for SQL Server | RDS Custom for SQL Server |
|-------------------------|--------------------|----------------------------|
| Publisher               | No                 | Yes                        |
| Distributor             | No                 | Yes                        |
| Pull Subscriber         | No                 | Yes                        |
| Push Subscriber         | Yes                | Yes                        |

RDS Custom mở rộng khả năng vượt xa RDS tiêu chuẩn bằng cách hỗ trợ các vai trò như Publisher và Distributor, vốn thường không được phép trên các bản RDS thông thường.  
Amazon Web Services, Inc.

#### 1.2 SQL Server Replication Types

| Replication Type     | Supported on RDS for SQL Server | Supported on RDS Custom | Notes |
|----------------------|---------------------------------|--------------------------|--------|
| Transactional        | Yes (as subscriber only)        | Yes                      | Phổ biến cho đồng bộ gần thời gian thực — Amazon Web Services, Inc. |
| Snapshot             | Yes (as subscriber only)        | Yes                      | Chụp lại trạng thái dữ liệu tại một thời điểm — Amazon Web Services, Inc. |
| Merge                | No                               | Yes (with limitations)   | Yêu cầu dùng hostname thay cho CNAME khi thay thế host — Amazon Web Services, Inc. |
| Peer-to-peer         | No                               | Yes (with limitations)   | Cần cấu hình hostname để tránh lỗi khi host replacement — Amazon Web Services, Inc. |

**Lưu ý:** Merge và peer-to-peer replication trên RDS Custom yêu cầu sử dụng hostname thay vì CNAME để tránh lỗi khi có thay thế host.  
Amazon Web Services, Inc.

---

## 2. Solution Overview & Architecture
Giải pháp gốc minh họa kiến trúc mẫu với hai instance RDS Custom trong cùng một vùng (region). Một instance đóng vai trò Publisher kiêm Distributor, trong khi instance còn lại đóng vai trò Subscriber. Replication được xử lý thông qua publication và subscription.  
Amazon Web Services, Inc.

Trước khi cấu hình replication, hãy đảm bảo:

- Cả hai instance RDS Custom đều được triển khai với cấu hình mạng và domain phù hợp (nếu dùng Kerberos).  
  Amazon Web Services, Inc.

- Tên server (`@@SERVERNAME`) trùng với hostname DNS được dùng cho replication.  
  Amazon Web Services, Inc.

- SQL Server Agent được bật trên cả publisher và subscriber.  
  Amazon Web Services, Inc.

- Kết nối mạng (cổng 1433) giữa các instance được cấu hình đúng.  
  Amazon Web Services, Inc.

---

## 3. Transactional Replication Configuration Guide
Below are the steps to set up transactional replication between RDS Custom for SQL Server instances.  
Amazon Web Services, Inc.

#### Step 1: Update the Server Name (`SERVERNAME`) if Needed
Connect to each instance (publisher and subscriber) and check the current value of `@@SERVERNAME`.

If the current server name does not match the hostname/CNAME you plan to use, execute:

```sql
SELECT @@SERVERNAME AS 'Current_Server_Name';
EXEC sp_dropserver 'old_server_name';
EXEC sp_addserver 'new_cname', 'local';
```

#### Step 2: Create the Publication on the Publisher:
```sql
CREATE DATABASE PublicationDB;
GO
USE PublicationDB;
GO
CREATE TABLE Tracker (
    Date DATE,
    RPO TIME,
    Status VARCHAR(255),
    PRIMARY KEY (RPO)
);
GO
INSERT INTO Tracker VALUES (CAST(GETDATE() AS Date), CAST(GETDATE() AS time(7)), 'Success');
GO

On the Subscriber:
CREATE DATABASE SubscriptionDB;
GO
```
#### Bước 3: Tạo Publication và Subscription
- Trên Publisher, mở Replication > New Publication Wizard
- Chọn database PublicationDB và chọn bảng Tracker làm article
- Tạo một subscription trỏ đến instance Subscriber
- Chọn push subscription, với agent chạy trên Distributor (có thể đặt trên cùng instance với Publisher nếu đã cấu hình)
- Sau khi hoàn tất cấu hình, bạn có thể theo dõi hoạt động replication bằng Replication Monitor

## 4. Advantages, Limitations & Considerations

#### Advantages
- Hỗ trợ replication gốc của SQL Server trên RDS Custom — không cần xây dựng hệ thống replication bên ngoài
- Cung cấp nhiều loại replication (transactional, snapshot, merge, peer-to-peer) để đáp ứng nhiều trường hợp sử dụng
- Giúp giảm tải workload phân tích khỏi hệ thống sản xuất

#### Limitations & Risks
- Merge và peer-to-peer replication yêu cầu cấu hình hostname và có thể gặp vấn đề khi thay thế host
- Độ trễ có thể xảy ra khi workload giao dịch cao
- Việc thay đổi tên server (@@SERVERNAME) yêu cầu khởi động lại và cần được thực hiện cẩn thận
- Các replication agent (Snapshot, Log Reader, Distribution) phải được giám sát để tránh lỗi

#### Practical Considerations
- Đảm bảo DNS/hostname ổn định — không phụ thuộc hoàn toàn vào CNAME khi có khả năng xảy ra host replacement
- Xác nhận SQL Server Agent được cấu hình auto-start
- Cấu hình các tài khoản Windows hoặc tài khoản domain phù hợp cho các replication agent (Snapshot Agent, Log Reader Agent, Distributor Agent)
- Giám sát độ trễ và lỗi replication thông qua SQL Server Replication Monitor

## Conclusion

Amazon RDS Custom for SQL Server allows you to use native SQL Server replication features that are not supported on standard RDS instances. You can deploy snapshot, transactional, merge, or peer-to-peer replication depending on your needs, with special attention to hostname configuration, server name settings, agent permissions, and network access.

For environments requiring data distribution across multiple databases, high availability, or separate analytical workloads, native replication on RDS Custom provides powerful benefits without the need to build an external replication solution.

## About the Author

**Sudhir Amin**
<img src="/images/Blog3.1.jpg" width="120" style="float:left; margin:0;" />

Sudhir là Kiến trúc sư giải pháp cao cấp (Senior Solutions Architect) tại Amazon Web Services, làm việc tại New York. Anh cung cấp hướng dẫn kiến trúc và hỗ trợ kỹ thuật cho các khách hàng doanh nghiệp trên nhiều lĩnh vực khác nhau, giúp họ đẩy nhanh quá trình chuyển đổi và ứng dụng điện toán đám mây.
Ngoài công việc, Sudhir đam mê bi-a (snooker) và các môn thể thao đối kháng như boxing và UFC. Anh cũng thích du lịch đến các khu bảo tồn thiên nhiên trên khắp thế giới để quan sát các loài động vật hoang dã trong môi trường tự nhiên của chúng. 

---


 **Mesgana Gormley**
 <img src="/images/Blog3.2.jpg" width="120" style="float:left; margin:0;" />

Mesgana là Kiến trúc sư giải pháp chuyên gia cơ sở dữ liệu cao cấp (Senior Database Specialist Solution Architect) thuộc bộ phận Worldwide Public Sector (WWPS) tại Amazon Web Services (AWS), làm việc cùng nhóm Amazon RDS. Cô tập trung vào việc cung cấp hướng dẫn kỹ thuật cho khách hàng AWS, hỗ trợ họ di chuyển, thiết kế, triển khai và tối ưu hóa các khối lượng công việc cơ sở dữ liệu quan hệ trên AWS một cách hiệu quả.
 Ngoài công việc, Mesgana yêu thích du lịch và dành thời gian bên gia đình, bạn bè.
