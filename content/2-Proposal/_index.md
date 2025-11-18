---
title: "Proposal"
date: 2025-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---


# Mini Food Social  
## A Serverless Social Platform with AI-Powered Recipe Generation

### 1. Executive Summary
The **Mini Food Social** project is designed as a modern, serverless web application for culinary enthusiasts to share food posts, upload images, and generate AI-based recipe suggestions. The platform supports up to **100 registered users** with authentication, CRUD functionality (create, read, update, delete posts), likes, comments, and AI integration.  

The system leverages **AWS Serverless Architecture** for scalability, low cost, and simplicity. The combination of **AWS Amplify**, **Amazon API Gateway**, **AWS Lambda**, **Amazon DynamoDB**, and **Amazon Bedrock** ensures end-to-end functionality with minimal operational overhead.

**AWS Services Used**
- **AWS Amplify**: Hosts Next.js web app and manages CI/CD.  
- **Amazon API Gateway**: Routes requests between frontend and backend.  
- **AWS Lambda**: Handles business logic and API endpoints.  
- **Amazon DynamoDB**: Stores user posts, likes, and comments.  
- **Amazon Cognito**: Manages user authentication.  
- **Amazon Bedrock (Claude Model)**: Generates creative recipes from user prompts.  
- **Amazon CloudFront + WAF + Route 53**: Ensures fast, secure content delivery.  

**Estimated Cost:** ~$16.70/month (~$200.40/year) without free tier.

---

### 2. Problem Statement
### What’s the Problem?
Existing recipe-sharing platforms are either static or rely on heavy infrastructure. They often lack:
- Personalized AI recipe generation.
- Serverless scalability and cost optimization.
- Secure authentication and lightweight architecture.

Managing infrastructure for dynamic social features like posts, likes, and AI generation requires significant effort and cost.

### The Solution
Mini Food Social solves these issues through **a fully serverless AWS stack**:
- AWS Amplify + Next.js for hosting and frontend logic.  
- Cognito for authentication and user management.  
- API Gateway connects to multiple Lambda functions (Post CRUD, User, AI Recipe).  
- DynamoDB stores post metadata and user interactions.  
- Bedrock (Claude) provides AI recipe generation via Lambda.  
- CloudFront + WAF + Route 53 secure the content globally.  

### Benefits and Return on Investment
- **Low Cost** – Pay only for usage.  
- **Fully Serverless** – No manual scaling or servers.  
- **AI-Enhanced Engagement** – Personalized recipe generation keeps users active.  
- **Secure** – Cognito authentication and data encryption by AWS.  

The project demonstrates scalable social architecture under $20/month while integrating AI seamlessly into user experience.

---

### 3. Solution Architecture
The Mini Food Social platform follows a **five-layer architecture**:

1. **Frontend (Amplify + Next.js)**:  
   - Users upload photos, create posts, and view feeds.  
   - Handles authentication via Cognito and fetches API data.  

2. **API Gateway + Lambda Router**:  
   - Routes requests (CRUD operations, AI requests).  
   - Lambda functions handle `createPost`, `getPosts`, `likePost`, and `generateRecipe`.  

3. **Database (DynamoDB)**:  
   - Stores users, posts, likes, and recipe results.  

4. **AI Integration (Bedrock)**:  
   - Claude model generates creative recipes based on user-uploaded photos or text prompts.  

5. **Security & Delivery Layer (CloudFront + WAF + Route 53)**:  
   - Protects the app from malicious traffic.  
   - Ensures low-latency delivery of assets.

**Architecture Diagram**
<img src="/images/2-Proposal/Untitled Diagram.drawio.png" alt="Your profile picture" width="800" height="500" />

---

### 4. Technical Implementation
**Implementation Phases**

- **Phase 1 – Research & Design (Month 0)**  
  - Define system requirements and AWS architecture.  
  - Study Bedrock integration for recipe generation.  

- **Phase 2 – Setup & Pricing (Month 1)**  
  - Use AWS Pricing Calculator to estimate total cost (~$16.70/month).  
  - Create GitLab repository and Amplify CI/CD pipeline.  

- **Phase 3 – Build & Integration (Month 2)**  
  - Develop Lambda APIs for CRUD and AI recipe endpoints.  
  - Configure DynamoDB tables and Cognito authentication flow.  

- **Phase 4 – Deployment & Testing (Month 3)**  
  - Deploy Amplify frontend and backend stack.  
  - Test API integration, AI outputs, and security.  

**Technical Requirements**
- **Frontend:** Next.js + AWS Amplify.  
- **Backend:** AWS Lambda, API Gateway, DynamoDB.  
- **AI Module:** AWS Lambda calling Amazon Bedrock (Claude) for text generation.  
- **Auth:** Amazon Cognito for login and JWT verification.  
- **Storage:** DynamoDB + optional S3 for image upload.  

---

### 5. Timeline & Milestones
| Phase | Duration | Description |
|-------|-----------|-------------|
| Month 0 | 1 month | Design system & architecture |
| Month 1 | 1 month | Pricing & setup of AWS Amplify + Cognito |
| Month 2 | 1 month | Develop API Gateway + Lambda + Bedrock integration |
| Month 3 | 1 month | Testing, deployment, and optimization |
| Post-Launch | Ongoing | Monitor, improve AI model prompts, collect feedback |

---

### 6. Budget Estimation
You can find the full budget on the [AWS Pricing Calculator](https://calculator.aws/#/estimate?id=abcd1234efgh5678).  
Or download the [Budget Estimation File](../attachments/budget_estimation_mfs.pdf).

#### Infrastructure Costs
| Service | Monthly Estimate | Description |
|----------|------------------|--------------|
| AWS Amplify | $3.00 | Web hosting & CI/CD |
| API Gateway | $2.50 | 20,000 requests/month |
| AWS Lambda | $2.00 | 50,000 invocations/month |
| DynamoDB | $1.20 | 1 GB storage |
| Cognito | $1.00 | 100 active users |
| Bedrock (Claude) | $5.00 | 500 AI recipe generations |
| CloudFront + WAF | $2.00 | CDN and basic firewall |

**Total Monthly:** ~$16.70  
**Total Annual:** ~$200.40  

---

### 7. Risk Assessment
#### Risk Matrix
| Risk | Impact | Probability | Mitigation |
|------|---------|--------------|-------------|
| High Bedrock Cost | Medium | Medium | Limit AI calls per user/day |
| API Gateway Bottlenecks | Medium | Low | Use caching and CloudFront |
| DynamoDB Hot Partition | Medium | Low | Implement balanced keys |
| Authentication Issues | Medium | Low | Use Cognito token refresh and multi-region backup |
| Over-usage | Low | Medium | Apply API throttling and budget alerts |

#### Contingency Plans
- Use fallback recipe templates if Bedrock API fails.  
- Migrate to DynamoDB on-demand mode for scalability.  
- Enable AWS Cost Explorer alerts for budget control.

---

### 8. Expected Outcomes
#### Technical Improvements
- Serverless architecture allows instant scalability.  
- AI integration enriches user interaction and creativity.  
- Minimal maintenance and infrastructure management.  

#### Long-Term Value
- Demonstrates AWS serverless and AI integration for education and startup use.  
- Reusable for future projects (social, content, or AI-based apps).  
- Foundation for AI-driven user personalization and recommendation systems.
