---
title: "Week 7 Worklog"
date: 2025-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---



### Week 7 Objectives:

* Understand the concepts and benefits of containerization in application development.  
* Learn how to build, manage, and deploy Docker containers.  
* Explore Amazon ECS (Elastic Container Service) and ECR (Elastic Container Registry).  
* Deploy a containerized web application using ECS Fargate.  
* Introduce CI/CD automation for container deployment pipelines.  

---

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ----------- | ---------------- | ------------------ |
| 2 | - Review the difference between Containers and Virtual Machines. <br> - Study the role of Docker in application packaging and isolation. <br> - **Practice:** <br>&emsp; + Install Docker Desktop. <br>&emsp; + Create a Dockerfile for a simple web app (Node.js or Python Flask). <br>&emsp; + Build and run the container locally. <br>| 20/10/2025 | 20/10/2025 | AWS Study Group |
| 3 | - Learn about Amazon Elastic Container Registry (ECR). <br> - **Practice:** <br>&emsp; + Create an ECR repository. <br>&emsp; + Tag and push the Docker image to ECR. <br>&emsp; + Verify image storage and permissions. <br>| 21/10/2025 | 21/10/2025 | AWS Study Group |
| 4 | - Explore Amazon Elastic Container Service (ECS) basics. <br> - **Practice:** <br>&emsp; + Create an ECS Cluster using Fargate launch type. <br>&emsp; + Define Task Definitions and Services. <br>&emsp; + Deploy the containerized app. <br>| 22/10/2025 | 22/10/2025 | AWS Study Group |
| 5 | - Integrate Load Balancing with ECS. <br> - **Practice:** <br>&emsp; + Configure Application Load Balancer (ALB). <br>&emsp; + Connect ECS service to ALB for public access. <br>&emsp; + Test high availability and scaling. <br>| 23/10/2025 | 23/10/2025 | AWS Study Group |
| 6 | - Automate deployments using AWS CodePipeline and CodeBuild. <br> - **Practice:** <br>&emsp; + Set up CI/CD pipeline to build Docker images. <br>&emsp; + Deploy updates automatically to ECS. <br>&emsp; + Test zero-downtime deployment. <br>| 24/10/2025 | 24/10/2025 | AWS Study Group |

---

### Week 7 Achievements:

* **Docker Fundamentals**  
  - Understood how containers differ from virtual machines and why they are lightweight.  
  - Created and tested Docker containers locally using custom Dockerfiles.  

* **ECR Image Management**  
  - Created and managed private ECR repositories.  
  - Successfully pushed and pulled Docker images from AWS ECR.  

* **ECS Deployment**  
  - Built and deployed containerized applications using ECS Fargate.  
  - Configured task definitions, services, and networking settings for ECS workloads.  

* **Load Balancing and Scaling**  
  - Integrated Application Load Balancer (ALB) with ECS services for public access.  
  - Verified automatic scaling and traffic distribution between containers.  

* **CI/CD Automation**  
  - Implemented a simple CI/CD pipeline using CodePipeline and CodeBuild.  
  - Automated image build and deployment process to ECS.  
  - Achieved efficient, repeatable, and zero-downtime container deployments.  
