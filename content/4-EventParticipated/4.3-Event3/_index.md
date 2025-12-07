---
title: "Event 3"
date: 2025-11-29
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---



# Summary Report: “AWS Well-Architected Security Pillar Workshop”

## Workshop Objectives

Join the course on the 5 security pillars of the AWS Well-Architected Framework, helping you build a strong security foundation and a comprehensive incident response process.

---

# Workshop Agenda & Key Highlights

## Morning Session (8:30 AM – 12:00 PM)

---

### 8:50 - 10h30 AM | Identity & Access Management,Detection

**Key Topics**
- Modern IAM architecture: Users, Roles, Policies  
- Avoiding long-term credentials  
- IAM Identity Center: SSO and permission sets  
- SCP (Service Control Policies) and permission boundaries for multi-account  
- MFA enforcement, credential rotation, Access Analyzer  
- CloudTrail , GuardDuty, Security Hub  
- Logging at every layer: VPC Flow Logs, ALB logs, S3 logs  
- Alerting and automation with EventBridge  
- Detection-as-Code (infrastructure + rules)  

**Hands-on Demo**
- IAM Policy validation  
- Access simulation  

**Key Takeaways**
- Least privilege reduces blast radius  
- IAM Identity Center optimizes multi-account security  
- SCPs enforce governance at the organization level  

---

### 9:55 - 10:10 AM | Coffee Break
- Chill
- Toilet

---

###  10:45 - 11:30 AM | Infrastructure Protection 

**Key Topics**
- VPC segmentation: public vs private placement  
- Security Groups vs NACLs: real-world use cases  
- WAF, Shield, Network Firewall  
- Workload protection: EC2, ECS/EKS security basics  

**Design Exercise**
- Designing a secure multi-tier VPC architecture  

**Key Takeaways**
- Defense in depth: layered security  
- Application protection against DDoS and OWASP Top 10  
- Centralized inspection with AWS Network Firewall  

---

###  11h30 - 12:10 AM | Data Protection

**Key Topics**
- AWS KMS: key policies, grants, rotation  
- Encryption at-rest and in-transit: S3, EBS, RDS, DynamoDB  
- Secrets Manager and Parameter Store: rotation models  
- Data classification and access guardrails  

**Hands-on Demo**
- Large-scale encryption deployment  
- Automated secret rotation  

**Key Takeaways**
- Encryption must be applied both at-rest and in-transit  
- Misconfigured key policies can cause outages  
- Secrets Manager reduces risks of hardcoded credentials  

---

### Summary & Q&A (11:40 AM - 12:00 PM)

**Summary Contents**
- Summary of the 5 Security Pillar components  
- Common pitfalls in Vietnamese enterprises  
- Learning roadmap: Security Specialty, SA Pro  

---

# Event Experience

### Security Foundation
- The AWS Shared Responsibility Model defines clear security boundaries  
- Identity is the first and strongest line of defense  
- Zero Trust Architecture is becoming the new standard  

### Technical Skills
- IAM governance ensures scalable security  
- KMS simplifies encryption across AWS services  
- Network isolation reduces attack surface  
- Security Hub + GuardDuty = continuous monitoring  

### Applying to Work
- Enforce MFA and least privilege IAM  
- Encrypt all critical data with KMS  
- Enable GuardDuty, CloudTrail, Config by default  
- Use multi-account architecture with Control Tower  
- Shift-left security in CI/CD pipelines  

---
