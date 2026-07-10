---
title: "Proposal"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 2. </b> "
---


# AI Resume Matching & Interview Preparation Platform
## A Web Application for CV and JD Matching on AWS 3-Tier Architecture

### 1. Executive Summary
The AI Resume Matching & Interview Preparation project aims to automate the recruitment process. The system allows for quick and accurate assessment of the match between a CV and a Job Description (JD). It is built on a scalable AWS 3-Tier architecture to optimize costs. The EC2 cluster (Backend + Worker) is responsible for analyzing CVs and JDs by calling the OpenAI API over the Internet.

### 2. Problem Statement
*Current Problem*
Manually evaluating a large number of CVs against JDs takes a massive amount of time for HR professionals. Furthermore, directly using AI services (like OpenAI) to analyze raw text often consumes a huge amount of tokens, leading to expensive operational costs.

*The Solution*
A Web application evaluating the fit between CVs and JDs based on the standard AWS 3-Tier architecture. The EC2 cluster (Backend + Worker) analyzes CVs and JDs by directly calling the OpenAI API over the Internet to optimize token consumption and save costs.

*Benefits and Return on Investment*
The system automates candidate screening, saving HR tens of hours per week. A short break-even period is expected due to optimized operational costs through Auto Scaling and High Availability.

### 3. Solution Architecture
The architecture is deployed following the 3-Tier standard on AWS, ensuring High Availability, security, and automation.

![AI Resume Matching Architecture](/images/2-Proposal/architecture.png)

*AWS Services Used*
- **Global & Edge Layer:** Content delivery network (CloudFront), WAF firewall, and authentication services are planned but not deployed (AWS account verification required). Uses Amazon S3 for general storage. Users interact via Internet Gateway (1) or "Upload via Pre-signed URL" directly to a separate S3 storage (S3 CV/JD Storage) (5).
- **Network & Load Balancing (Inbound):** VPC 10.0.0.0/16 as the foundation. Internet Gateway (IGW) acts as the single gateway connecting to the Internet for both Inbound and Outbound traffic (via NAT Gateway). Application Load Balancer (ALB) sits between Availability Zones, receiving traffic from IGW and distributing it to the Auto Scaling Group cluster.
- **Application Tier:** EC2 Cluster (Backend + Worker) placed in closed Private App Subnets (Private App Subnet A & Private App Subnet B), spanning 2 Availability Zones (AZ A & AZ B) and managed by an Auto Scaling Group (ASG) for elastic scaling. Internal communication: EC2 (AZ A) connects with S3 storage and SQS services (6), followed by Dead Letter Queue (DLQ). OpenAI API flow (AZ B) is executed by EC2 (AZ B) routing outward through the NAT Gateway in Public Subnet B to call the Internet Gateway.
- **Outbound & Internal Network:** There are **two NAT Gateways**, one in Public Subnet A and one in Public Subnet B, ensuring High Availability for Outbound traffic from Private Subnets. Communication to SQS and S3 is routed over the network; no VPC Endpoints are present.
- **Database Tier:** Uses Amazon RDS PostgreSQL with Multi-AZ configuration. Two Private DB Subnets (Private DB Subnet A & Private DB Subnet B) protected by a Security Group. RDS Primary (Master) in AZ A. RDS Standby Replica in AZ B with continuously synchronized data (dashed line). Connection flow: EC2 in AZ A connects directly to RDS Primary (7). EC2 in AZ B connects to RDS Standby Replica via RDS Endpoints (dashed line).
- **Management & Monitoring:** A "Security & Management Regional" cluster includes AWS Systems Manager, Amazon CloudWatch (logs), and AWS Secrets Manager (API Key).
- **Deployment:** Source code located on GitHub (Manual Deployment) is designated for manual deployment. Not using AWS CodeBuild or AWS CodePipeline automatically in the current architecture.

### 4. Technical Implementation
*Implementation Phases*
1. *Research & Architecture Design*: Requirements analysis, AWS architecture diagramming, and AI prompt scripting.
2. *Infrastructure Foundation*: Deploy VPC, Subnets, Route Tables, IGW, NAT Gateways, and RDS.
3. *App Development & AI Integration*: Write Backend/Worker code on EC2, configure OpenAI API calls.
4. *Frontend & Deployment*: Manual deployment from GitHub, host static Frontend on S3.

*Technical Requirements*
Solid knowledge of AWS Networking (VPC, Subnetting) and Multi-AZ Database administration. Backend programming skills (Python/Node.js) for OpenAI integration.

### 5. Timeline & Milestones
- *Phase 1 (Weeks 1-2):* Architecture design, VPC network, and security configuration.
- *Phase 2 (Weeks 3-5):* Build Database tier (RDS) and Application tier (ASG, EC2), integrate AI.
- *Phase 3 (Weeks 6-7):* Frontend development, S3 storage configuration.
- *Phase 4 (Week 8):* Manual deployment, load testing, and documentation completion.

### 6. Budget Estimation
*Infrastructure Costs (Monthly Estimate)*
- **Amazon EC2 & ASG:** Depends on load, base cost for 2 EC2s (t3 instance family: t3.micro/t3.small).
- **Amazon RDS (Multi-AZ):** Highest cost due to running 2 nodes simultaneously (Primary & Standby).
- **NAT Gateway & Data Transfer:** Billed hourly and per processed data volume.
- **WAF, CloudFront & S3:** Fees based on traffic (Requests) and static storage.
- **OpenAI API:** Optimized by the pre-processing service.

### 7. Risk Assessment
*Risk Matrix*
- OpenAI API Connection Error: High impact, low probability.
- System Overload from CV volume spike: Medium impact, low probability (ASG configured).
- Budget Overruns: Medium impact, medium probability.

*Mitigation Strategies*
- Configure Auto Scaling Group (ASG) to scale elastically based on CPU/Memory utilization.
- Setup CloudWatch Billing Alarms to trigger instantly when costs exceed thresholds.
- Utilize message queues (Amazon SQS) to asynchronously process heavy CV evaluation tasks.

### 8. Expected Outcomes
*Technical Improvements*: A secure, highly available standard 3-Tier system, with Database Failover capabilities and auto-scaling.
*Long-term Value*: Becomes a powerful tool for HR departments, reducing hiring time and optimizing processes.