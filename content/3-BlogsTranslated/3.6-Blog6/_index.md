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
Modern applications often require reliable data distribution and high availability across multiple databases to support mission-critical business operations. SQL Server Replication enables database administrators (DBAs) to automatically distribute data across databases in near real-time, helping offload heavy read workloads from production systems and synchronizing data across regions or different database environments.

Amazon RDS Custom for SQL Server is a managed service that combines the flexibility of a self-managed database with the automation benefits of a fully managed offering. With RDS Custom, you can leverage native SQL Server replication features while AWS handles infrastructure tasks such as backups, patching, snapshots, and monitoring.  
This blog explores how to configure SQL Server Replication on RDS Custom, including supported replication types (snapshot, transactional, merge, peer-to-peer) and step-by-step instructions to configure distributors, publications, and subscriptions.  
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

RDS Custom extends the capabilities beyond standard RDS by supporting roles such as Publisher and Distributor, which are typically disallowed on regular RDS instances.  
Amazon Web Services, Inc.

#### 1.2 SQL Server Replication Types

| Replication Type     | Supported on RDS for SQL Server | Supported on RDS Custom | Notes |
|----------------------|---------------------------------|--------------------------|-------|
| Transactional        | Yes (as subscriber only)        | Yes                      | Common for near real-time synchronization — Amazon Web Services, Inc. |
| Snapshot             | Yes (as subscriber only)        | Yes                      | Captures a full data state at a specific moment — Amazon Web Services, Inc. |
| Merge                | No                               | Yes (with limitations)   | Requires hostname instead of CNAME when host replacement occurs — Amazon Web Services, Inc. |
| Peer-to-peer         | No                               | Yes (with limitations)   | Needs hostname configuration to avoid host replacement issues — Amazon Web Services, Inc. |

**Note:** Merge and peer-to-peer replication on RDS Custom require using hostnames instead of CNAMEs to prevent issues during host replacement.  
Amazon Web Services, Inc.

---

## 2. Solution Overview & Architecture
The original solution showcases a sample architecture with two RDS Custom instances in the same region. One instance acts as both Publisher and Distributor, while the second instance serves as the Subscriber. Replication is handled through publications and subscriptions.  
Amazon Web Services, Inc.

Before configuring replication, ensure:

- Both RDS Custom instances are deployed with proper networking and domain setup (if using Kerberos).  
  Amazon Web Services, Inc.

- The server name (`@@SERVERNAME`) matches the DNS hostname used for replication.  
  Amazon Web Services, Inc.

- SQL Server Agent is enabled on both the publisher and subscriber.  
  Amazon Web Services, Inc.

- Network connectivity (port 1433) between instances is properly configured.  
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
#### Step 3: Create the Publication and Subscription

- On the Publisher, open Replication > New Publication Wizard
- Select the PublicationDB database and choose the Tracker table as the article
- reate a subscription pointing to the Subscriber instance
- Choose a push subscription, with the agent running on the Distributor (which can be hosted on the same instance as the publisher if configured)
- After setup, you can monitor replication activity using Replication Monitor.

## 4. Advantages, Limitations & Considerations

#### Advantages
- Supports native SQL Server replication on RDS Custom — no need to build an external replication system
- Provides multiple replication types (transactional, snapshot, merge, peer-to-peer) to meet different use cases
- Helps offload analytical workloads from the production system

#### Limitations & Risks
- Merge and peer-to-peer replication require hostname configuration and may encounter issues during host replacement
- Latency may occur under heavy transactional workloads
- Modifying the server name (@@SERVERNAME) requires a restart and must be done carefully
- Replication agents (Snapshot, Log Reader, Distribution) must be monitored to avoid failures

#### Practical Considerations
- Ensure DNS/hostname stability — do not rely solely on CNAMEs if host replacement may occur
- Confirm SQL Server Agent is configured for auto-start
- Configure appropriate Windows or domain accounts for replication agents (Snapshot Agent, Log Reader Agent, Distributor Agent)
- Monitor latency and replication errors through SQL Server Replication Monitor

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