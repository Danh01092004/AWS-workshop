---
title: "Blog 5"
date: 2025-01-01
weight: 5
chapter: false
pre: " <b> 3.5. </b> "
---

# AWS for Database: Real-time Iceberg Ingestion with AWS DMS

**By Caius Brindescu – June 4, 2025**

*Tags: AWS Database, AWS DMS, Apache Iceberg, Data & Analytics, Industries*

## Introduction

Các nền tảng dữ liệu hiện đại ngày càng yêu cầu khả năng truy cập dữ liệu mới với độ trễ thấp để hỗ trợ phân tích thời gian thực và ra quyết định nhanh chóng. Tuy nhiên, nhiều tổ chức gặp khó khăn trong việc liên tục ingest các thay đổi (insert, update, delete) từ các cơ sở dữ liệu giao dịch vào data lake trong khi vẫn duy trì tính nhất quán mạnh mẽ.

Apache Iceberg là một định dạng bảng mở cung cấp ACID transactions, mở rộng schema linh hoạt, truy vấn time-travel, và khả năng tương thích với nhiều engine.  
Trong bài viết này (được viết bởi Caius Brindescu với sự hợp tác của AWS), chúng tôi thảo luận cách xây dựng pipeline dữ liệu gần real-time bằng **AWS Database Migration Service (DMS)** để thu thập dữ liệu thay đổi (CDC) từ cơ sở dữ liệu SQL và ingest vào các bảng Iceberg—đảm bảo tính nhất quán, chịu lỗi, và tích hợp mượt với các hệ thống downstream như Snowflake.  
Amazon Web Services, Inc.

---

## 1. What is AWS DMS and Why It Matters

AWS Database Migration Service (DMS) là dịch vụ quản lý cho phép di chuyển và đồng bộ dữ liệu giữa các hệ quản trị cơ sở dữ liệu khác nhau.

DMS hỗ trợ hai chế độ chính:

- **Full Load** – sao chép toàn bộ dữ liệu ban đầu  
- **CDC (Change Data Capture)** – thu thập insert, update và delete gần real-time  

Kết hợp Full Load + CDC giúp các bảng Iceberg được cập nhật liên tục với độ trễ thường dưới 5 giây.  
Amazon Web Services, Inc.

---

## 2. Pipeline Architecture: SQL → AWS DMS → Iceberg

#### 2.1 High-Level Architecture
Một pipeline điển hình như sau:

**Source DB (MySQL/PostgreSQL) → AWS DMS → Iceberg Table on S3 → Downstream Analytics (Snowflake, Athena, Spark)**

Cơ sở dữ liệu giao dịch đóng vai trò nguồn sinh ra các sự kiện thay đổi. DMS xử lý full load + CDC, và Iceberg lưu trữ dữ liệu trong định dạng bảng mở có khả năng mở rộng.  
Amazon Web Services, Inc.

#### 2.2 Components and Roles

| Component | Role |
|----------|------|
| Source Database | Sinh ra các sự kiện insert/update/delete |
| AWS DMS | Thực hiện full load + CDC và stream dữ liệu |
| Iceberg Table on S3 | Lưu trữ bảng ACID với khả năng truy cập từ nhiều engine |
| Merge/Upsert Logic | Áp dụng các thay đổi CDC lên bảng |
| Downstream Systems | Snowflake, Athena, Spark phục vụ phân tích |

---

## 3. Step-by-Step Setup

#### 3.1 Creating DMS Endpoints

- **Source Endpoint:** Kết nối tới cơ sở dữ liệu SQL (MySQL/PostgreSQL)  
- **Target Endpoint:** Trỏ đến vị trí S3 chứa dữ liệu Iceberg  

Cấu hình mẫu bao gồm hostname, port, username, password.

#### 3.2 Creating a Replication Task

Chọn chế độ **Full Load + CDC**  
Chọn bảng cần sao chép  
Thiết lập batch size nhỏ để giảm độ trễ  
Bật tùy chọn large objects nếu cần (LOB/JSON)

Khi chạy, DMS sẽ:

- Thực hiện full load ban đầu  
- Liên tục đọc log của source  
- Gửi thay đổi sang nơi staging  

#### 3.3 Handling DMS Output and Writing to Iceberg

DMS ghi các bản ghi thay đổi (thường ở dạng JSON/CSV) vào staging, bao gồm cột `action`.

Ví dụ dữ liệu CDC:

| id | name  | action |
|----|--------|---------|
| 1 | Alice | INSERT |
| 2 | Bob | UPDATE |
| 3 | Carol | DELETE |

Áp dụng thay đổi vào Iceberg bằng câu lệnh **MERGE**:

```sql
MERGE INTO iceberg_table t
USING staging_table s
ON t.id = s.id
WHEN MATCHED AND s.action = 'DELETE' THEN DELETE
WHEN MATCHED THEN UPDATE SET name = s.name
WHEN NOT MATCHED THEN INSERT (id, name) VALUES (s.id, s.name);
```

## Conclusion

Building a real-time data ingestion pipeline with AWS DMS and Apache Iceberg enables organizations to keep analytical datasets fresh, consistent, and scalable. By combining full-load initialization with continuous CDC streaming, teams can ensure low-latency updates while benefiting from Iceberg’s ACID guarantees and multi-engine interoperability. This architecture not only improves decision-making but also provides a future-proof foundation for modern analytics workloads.

## About the Author

**Caius Brindescu**
<img src="/images/Blog2.1.png" width="100" style="float:left; margin:0;" />

 Caius Brindescu là Kỹ sư chính (Principal Engineer) tại Etleap, chuyên triển khai các giải pháp dữ liệu thời gian thực. Ông hợp tác với AWS để xây dựng các pipeline sử dụng AWS DMS và Apache Iceberg, hướng đến việc giúp doanh nghiệp đạt khả năng xử lý dữ liệu gần real-time và mở rộng hiệu quả.

---


 **Mahesh Kansara**
 <img src="/images/Blog2.2.jpeg" width="100" style="float:left; margin:0;" />

 Mahesh là quản lý kỹ thuật cơ sở dữ liệu tại Amazon Web Services (AWS). Anh làm việc chặt chẽ với các nhóm phát triển và kỹ sư để cải thiện các dịch vụ di trú và sao chép dữ liệu. Đồng thời, anh cũng hợp tác với khách hàng để cung cấp hướng dẫn và hỗ trợ kỹ thuật cho nhiều dự án cơ sở dữ liệu và phân tích, giúp họ nâng cao giá trị của các giải pháp khi sử dụng AWS.
