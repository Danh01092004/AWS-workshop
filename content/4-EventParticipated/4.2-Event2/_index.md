---
title: "Event 2"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# Summary Report: “DevOps on AWS Workshop”

### Event Objectives

- Introduce DevOps culture, principles, and best practices  
- Provide hands-on knowledge of AWS DevOps services for CI/CD  
- Demonstrate Infrastructure as Code (IaC) using CloudFormation and CDK  
- Explore containerization and orchestration on AWS  
- Present monitoring, observability, and incident response techniques  
- Share real-world DevOps case studies and career direction

---

# Workshop Agenda & Key Highlights

## Morning Session (8:30 AM – 12:00 PM)

---

### 8:30 – 9:00 AM | Welcome & DevOps Mindset

### Topics
- **Recap of previous AI/ML session** and its relationship with DevOps  
- Introduction to **DevOps culture**, collaboration, and feedback loops  
- Key DevOps metrics:  
  - **DORA** metrics (Lead Time, Deployment Frequency, Change Failure Rate, MTTR)  
  - Importance of continuous improvement and reliability  

**Highlights:**
- Emphasized DevOps as a cultural shift, not just technology  
- Demonstrated how AI/ML workflows integrate into DevOps pipelines  
- Clarified why DevOps improves speed, stability, and organizational alignment  

---

### 9:00 – 10:30 AM | AWS DevOps Services – CI/CD Pipeline

### Core Components
- **Source Control** with AWS CodeCommit  
  - Git strategies: **GitFlow**, **Trunk-based development**, branch protection  
- **Build & Test** with CodeBuild  
  - Buildspec configuration, unit tests, integration tests  
- **Deployments** with CodeDeploy  
  - Deployment strategies: **Blue/Green**, **Canary**, **Rolling updates**  
- **Orchestration** using AWS CodePipeline  
  - Automated multi-stage pipelines (Source → Build → Test → Deploy)

### Demo
- End-to-end CI/CD pipeline from commit → build → deploy  
- Blue/Green deployment with automated rollback  

**Key takeaways:**
- CI/CD improves release reliability and reduces manual effort  
- Deployment strategies significantly reduce downtime and risks  
- CodePipeline provides full automation with minimal operational overhead  

---

### 10:30 – 10:45 AM | Break

---

### 10:45 AM – 12:00 PM | Infrastructure as Code (IaC)

### Topics Covered
- **AWS CloudFormation**
  - Templates, stacks, drift detection, and stack lifecycle  
- **AWS CDK (Cloud Development Kit)**
  - High-level constructs, reusable patterns, multi-language support  
- **Side-by-side comparison**
  - Declarative (CloudFormation) vs programmatic (CDK)

### Demo
- Deploying infrastructure using **CloudFormation templates**  
- Deploying the same architecture using **AWS CDK**  

**Discussion: Choosing IaC Tools**
- CloudFormation: stability, explicit control  
- CDK: productivity, abstraction, reusability  

---

### 12:00 – 1:00 PM | Lunch Break (Self-arranged)

---

# Afternoon Session (1:00 PM – 5:00 PM)

---

### 1:00 – 2:30 PM | Container Services on AWS

### Topics
- **Docker Fundamentals**
  - Microservices, container lifecycle, Dockerfile best practices  
- **Amazon ECR**
  - Image storage, vulnerability scanning, lifecycle policies  
- **Amazon ECS & Amazon EKS**
  - Cluster management, service scaling, orchestration patterns  
  - EC2 vs Fargate launch types  
- **AWS App Runner**
  - Simplified deployment for containerized applications

### Demo & Case Study
- Deploying microservices across **ECS**, **EKS**, and **App Runner**  
- Comparison of complexity, cost, and developer experience  

**Highlights:**
- Understanding which container service to choose for each use case  
- Importance of container scanning and image lifecycle management  
- Real-world example of migrating monoliths to microservices  

---

### 2:30 – 2:45 PM | Break

---

### 2:45 – 4:00 PM | Monitoring & Observability

### Topics
- **Amazon CloudWatch**
  - Metrics, logs, alarms, dashboards, anomaly detection  
- **AWS X-Ray**
  - Distributed tracing and performance bottleneck analysis  
- **End-to-end observability workflow**
  - Collect → Analyze → Visualize → Alert

### Demo
- Building a **full-stack observability** dashboard  
- Tracing a request through microservices using X-Ray  

**Best Practices**
- Alert fatigue prevention  
- Dashboards for SRE/DevOps teams  
- Structured logs and correlation IDs  

---

### 4:00 – 4:45 PM | DevOps Best Practices & Case Studies

### Topics
- Deployment techniques: **Feature flags**, **A/B testing**, **progressive delivery**  
- Testing automation: unit, integration, load testing in CI/CD  
- Incident response and blameless postmortems  
- Startup and enterprise DevOps transformation case studies

**Highlights:**
- How high-performance teams maintain reliability at scale  
- Why postmortems drive continuous improvement  
- Practical examples of real DevOps transformations on AWS  

---

### 4:45 – 5:00 PM | Q&A & Wrap-up

### Closing Items
- DevOps career pathways and required skill sets  
- Recommended AWS certifications (Developer, SysOps, DevOps Engineer)  
- Final discussion and networking  

---

# Key Takeaways

### DevOps Culture
- Collaboration, automation, and continuous learning are essential  
- DORA metrics provide clarity on performance and improvement areas  

### Technical Skills
- CI/CD pipelines reduce deployment risks and shorten release cycles  
- CloudFormation and CDK simplify infrastructure provisioning  
- ECS, EKS, and App Runner enable scalable container deployment  
- Observability ensures reliability and rapid incident response  

### Applying to Work
- Adopt trunk-based development for faster release cycles  
- Implement CI/CD pipelines with automated testing  
- Use IaC to enforce consistency and reduce configuration drift  
- Improve system reliability using monitoring dashboards and tracing tools  

---

# Event Experience

### Learning from Experts
- Speakers shared valuable insights into DevOps culture and tooling  
- Use cases and demos made the concepts practical and easy to apply  

### Hands-on Understanding
- Walkthrough of CI/CD pipelines provided clarity on real-world workflows  
- IaC demos highlighted differences between CloudFormation and CDK  
- Container deployment comparison gave a clearer decision-making framework  

### Networking and Discussion
- Opportunities to exchange experiences with other developers and engineers  
- Discussions focused on automation, reliability, and scaling challenges  

### Lessons Learned
- DevOps requires both cultural and technical adoption  
- Monitoring and observability are essential for operating distributed systems  
- Choosing the right container orchestration model depends on team maturity and workload  

---

### Event Photos  
*Add your workshop images here*

> Overall, the “DevOps on AWS” workshop provided a comprehensive understanding of modern DevOps workflows, tools, and best practices, helping me build more reliable, scalable, and automated systems.
