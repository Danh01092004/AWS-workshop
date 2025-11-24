---
title: "Event 3"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 4.3. </b> "
---

# Summary Report: “Security on AWS Workshop”

### Event Objectives

- Implement MFA and IAM least privilege  
- Encrypt all critical data with KMS  
- Enable GuardDuty, CloudTrail, Config by default  
- Use multi-account architecture with Control Tower 

---

# Workshop Agenda & Key Highlights

# Morning Session (8:30 AM – 12:00 PM)

---

### 8:30 – 9:00 AM | Welcome & Security Landscape

### Topics
- Recap of previous Cloud & DevOps sessions  
- Overview of **AWS Shared Responsibility Model**  
- Emerging cloud threats & Vietnam cybersecurity context  

**Highlights:**
- Clarified boundaries between AWS security and customer responsibilities  
- Discussed growing threats such as phishing, misconfigurations, data leaks  
- Emphasized need for automation and zero-trust principles  

---

### 9:00 – 10:30 AM | Identity & Access Management (IAM)

### Core Components
- IAM structure: **Users**, **Roles**, **Groups**, **Policies**  
- Permission Boundaries & Service Control Policies (SCPs)  
- IAM Identity Center for centralized workforce access  
- MFA enforcement, credential rotation, and auditing best practices  

### Demo
- Creating and validating IAM policies  
- Restricting access using least privilege  

**Key Takeaways**
- Least-privilege access significantly reduces blast radius  
- IAM Identity Center improves security for multi-account environments  
- SCPs enforce governance at the organization level  

---

### 10:30 – 10:45 AM | Coffee Break
- Chill
- Tolet

---

### 10:45 AM – 12:00 PM | Network Security

### Topics Covered
- VPC design best practices  
- Public vs Private subnets, NAT, subnet isolation  
- **Security Groups** vs **Network ACLs**  
- AWS WAF, Shield, and Network Firewall overview  

### Exercise
- Designing a secure, multi-tier VPC architecture  

**Discussion**
- Layered network defense (defense in depth)  
- Protecting applications against DDoS, OWASP Top 10  
- Centralized inspection using AWS Network Firewall  

---

### 12:00 – 1:00 PM | Lunch Break (Self-arranged)

---

# Afternoon Session (1:00 PM – 5:00 PM)

---

### 1:00 – 2:30 PM | Data Protection & Encryption

### Topics
- **AWS KMS**: key policies, rotation, envelope encryption  
- Encryption options for:  
  - **S3**, **EBS**, **RDS**, **DynamoDB**  
- Secrets Management using AWS Secrets Manager  
- Certificate management using ACM  

### Demo
- Implementing encryption at scale  
- Automating secret rotation  

**Highlights:**
- Encryption must be applied both **at rest** and **in transit**  
- Poor key policy configuration can cause major outages  
- Secrets Manager reduces risks caused by hardcoded credentials  

---

### 2:30 – 2:45 PM | Break
- Chill with homie

---

### 2:45 – 4:00 PM | Security Monitoring & Incident Response

### Topics
- AWS Security Hub, GuardDuty, Config, CloudTrail, Detective  
- Continuous compliance & threat detection  
- Building an incident response lifecycle  

### Demo
- Operating a Security Operations Dashboard  
- Investigating threats using GuardDuty + Detective  

**Best Practices**
- Enable CloudTrail organization-wide  
- Use Config Rules to detect misconfiguration  
- Automate alerts with SNS, EventBridge, and Lambda  

---

### 4:00 – 4:30 PM | Compliance & Governance

### Topics
- Major standards: **GDPR, HIPAA, PCI-DSS, SOC 2, ISO 27001**  
- AWS Control Tower & Organizations  
- Governance for multi-account structures  
- Case Study: Enterprise multi-account security model  

**Highlights**
- Compliance != Security (need both)  
- Control Tower enforces guardrails for account lifecycle  
- Multi-account is essential for isolation & least privilege  

---

### 4:30 – 4:50 PM | AWS Well-Architected Security Pillar

### Topics
- Identity, Detection, Infrastructure, Data, Response  
- Security automation & DevSecOps  
- Zero Trust Architecture  
- Cost optimization for security controls  

**Highlights**
- Shift-left security in CI/CD  
- Identity is the foundation of Zero Trust  
- Automation reduces operational noise and mistakes  

---

### 4:50 – 5:00 PM | Closing Remarks

### Closing Items
- Key takeaways from the AWS Cloud Mastery Series  
- Advanced learning and certification roadmap  
- Networking and group discussion  

---

# Key Takeaways

### Security Foundations
- Shared Responsibility Model defines clear security boundaries  
- Identity is the first and strongest line of defense  

### Technical Skills
- IAM governance ensures scalable security  
- KMS simplifies encryption across AWS services  
- Network isolation reduces attack surfaces  
- Security Hub + GuardDuty = continuous monitoring  

### Applying to Work
- Implement MFA and IAM least privilege  
- Encrypt all critical data with KMS  
- Enable GuardDuty, CloudTrail, Config by default  
- Use multi-account architecture with Control Tower  

---

# Event Experience

### Expert Knowledge
- Real-world examples of cloud breaches  
- Deep dive into AWS security controls  
- Clear explanation of IAM and encryption concepts  

### Practical Learning
- Hands-on IAM and KMS exercises  
- VPC security design session  
- Incident investigation demo  

### Networking
- Discussions with cloud engineers & security analysts  
- Shared challenges around compliance & scaling security  

### Lessons Learned
- Misconfigurations are the #1 cause of cloud incidents  
- Security must be continuous and automated  
- Zero Trust is becoming the new standard  

---

### Event Photos  
*Add your workshop images here*
