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

Modern data platforms increasingly require the ability to access fresh data with low latency to support real-time analytics and rapid decision-making. However, many organizations struggle to continuously ingest changes (insert, update, delete) from transactional databases into their data lakes while maintaining strong consistency guarantees.

Apache Iceberg is an open table format that brings ACID transactions, schema evolution, time-travel queries, and multi-engine interoperability.  
In this post (guest-authored by Caius Brindescu in collaboration with AWS), we discuss how to build a near real-time data pipeline using **AWS Database Migration Service (DMS)** to capture change data (CDC) from SQL databases and ingest it into Iceberg tables—ensuring consistency, fault tolerance, and seamless integration with downstream systems like Snowflake.  
Amazon Web Services, Inc.

---

## 1. What is AWS DMS and Why It Matters

AWS Database Migration Service (DMS) is a managed service that migrates and synchronizes data across heterogeneous database engines.

DMS supports two primary modes:

- **Full Load** – initial bulk copy from source to destination  
- **CDC (Change Data Capture)** – captures inserts, updates, and deletes in near real-time  

Combining Full Load + CDC allows Iceberg tables to stay continuously updated with latency typically below 5 seconds.  
Amazon Web Services, Inc.

---

## 2. Pipeline Architecture: SQL → AWS DMS → Iceberg

#### 2.1 High-Level Architecture
A typical pipeline looks like:

**Source DB (MySQL/PostgreSQL) → AWS DMS → Iceberg Table on S3 → Downstream Analytics (Snowflake, Athena, Spark)**

The transactional database acts as the origin point of change events. DMS handles the full load + CDC, and Iceberg stores the data in a scalable open table format.  
Amazon Web Services, Inc.

#### 2.2 Components and Roles

| Component | Role |
|----------|------|
| Source Database | Generates insert/update/delete events |
| AWS DMS | Performs full load + CDC and streams data |
| Iceberg Table on S3 | ACID table storage with multi-engine access |
| Merge/Upsert Logic | Applies CDC changes to the table |
| Downstream Systems | Snowflake, Athena, Spark for analytics |

---

## 3. Step-by-Step Setup

#### 3.1 Creating DMS Endpoints

- **Source Endpoint:** Connects to SQL database (MySQL/PostgreSQL)  
- **Target Endpoint:** Points to S3 location storing Iceberg data  

Sample configuration includes hostname, port, username, and password.

#### 3.2 Creating a Replication Task

Select **Full Load + CDC** mode  
Choose specific tables  
Set small batch sizes for low latency  
Enable large object options if necessary (LOB/JSON)

When executed, DMS will:

- Perform initial full load  
- Continuously read source logs  
- Send changes to target staging  

#### 3.3 Handling DMS Output and Writing to Iceberg

DMS writes change records (often JSON/CSV) into staging, including an `action` column.

Example CDC staging:

| id | name  | action |
|----|--------|---------|
| 1 | Alice | INSERT |
| 2 | Bob | UPDATE |
| 3 | Carol | DELETE |

Apply changes to Iceberg using a **MERGE** statement:

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



