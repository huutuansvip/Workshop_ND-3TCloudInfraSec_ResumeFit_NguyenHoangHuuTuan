---
title: "3. Cost Breakdown"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 5.12. </b> "
---

This cost breakdown is estimated using the **AWS Pricing Calculator** for deploying the system in the **US East (N. Virginia) – us-east-1** region. The estimation is based on **AWS On-Demand** pricing for an operational time of **730 hours/month (24/7)**. Since the system is designed solely for demonstration and project evaluation purposes, the expected traffic is extremely low. Cost optimization models such as Reserved Instances or Savings Plans are not applied.

### Estimated Monthly Deployment Cost

| No. | AWS Service | Configuration | Quantity | Estimated Monthly Cost (USD) | Notes | Total (USD) |
|---|---|---|---|---|---|---|
| 1 | Amazon VPC | 01 VPC, 01 IGW, 02 Public Subnets, 04 Private Subnets, Route Tables | 1 | 0.00 | Basic networking and routing services are free. | 0.00 |
| 2 | AWS Security Group | Firewall rules to protect resources | 1 | 0.00 | Included security feature, no additional charge. | 0.00 |
| 3 | NAT Gateway | Processing traffic from Private Subnets to the Internet (~1 GB data) | 2 | 32.85 | $0.045/hour * 730 hours + $0.045/GB | 65.70 |
| 4 | Amazon EC2 | t3.micro (Linux), On-Demand | 3 | 7.59 | $0.0104/hour * 730 hours | 22.78 |
| 5 | Amazon EBS | gp3, 30 GB/volume | 3 | 2.40 | $0.08/GB-month | 7.20 |
| 6 | Auto Scaling Group | 01 Launch Template, 01 ASG | 1 | 0.00 | ASG service is free (only underlying EC2/EBS are billed). | 0.00 |
| 7 | Application Load Balancer | 01 ALB, 01 Target Group (Estimated < 1 LCU) | 1 | 22.27 | $0.0225/hour ($16.43) + base LCU charge. | 22.27 |
| 8 | Amazon RDS | Single-AZ, db.t3.micro, 20 GB gp3 | 1 | 14.71 | Instance: $12.41 ($0.017/hour), Storage: $2.30 | 14.71 |
| 9 | Amazon S3 | Standard Storage (5 GB) | 1 | 0.12 | $0.023/GB-month | 0.12 |
| 10 | Amazon SQS | Standard Queue & DLQ (< 1 million requests) | 1 | 0.00 | Within the Free Tier limits. | 0.00 |
| 11 | AWS Secrets Manager | 01 Secret (< 10,000 API calls) | 1 | 0.40 | $0.40/secret/month | 0.40 |
| 12 | Amazon Cognito | User management (< 50,000 MAU) | 1 | 0.00 | Within the Free Tier limits (< 50,000 MAU). | 0.00 |
| 13 | Amazon CloudWatch | Basic Metrics & Logs (< 5 GB) | 1 | 0.00 | Within the Free Tier limits. | 0.00 |
| 14 | AWS Systems Manager | Session Manager (secure access management) | 1 | 0.00 | Included connection feature, no additional charge. | 0.00 |

### Cost Analysis

**1. Total Monthly Deployment Cost:**
Based on the estimation table, the total cost to maintain the system running 24/7 for one month is **$133.18**.

**2. Highest Cost Drivers:**
- **NAT Gateway** is the most expensive service, accounting for approximately **49.3%** of the total cost ($65.70). Deploying 02 NAT Gateways to ensure High Availability for the Private Subnets across 2 Availability Zones significantly increases the fixed hourly charge.
- **Compute (EC2 & ALB)** is the second-largest cost category. The Application Load Balancer ($22.27) and the 3 EC2 t3.micro instances ($22.78) for the Web/App servers contribute notably, as they must remain continuously active to handle incoming traffic.

**3. Suitability with the AWS $200 Credit Limit:**
The estimated total cost is **$133.18/month**, which is well within the $200 AWS Credit limit. The system is perfectly suited to meet the objectives of running the demo and evaluating the project for a month without the risk of exceeding the budget. However, if the project evaluation period extends beyond 1.5 months, the budget will be depleted.

**4. Proposed Cost Optimization Measures (Without Altering Architecture):**
Although the system complies with the $200 budget, the following practices can be applied to further optimize costs without changing the current architectural design:
- **Optimize Operating Hours (Start/Stop Scheduling):** Since the system is only for demo purposes, it does not need to run 24/7. AWS Lambda or EventBridge can be configured to automatically stop the EC2 instances and RDS during non-working hours (e.g., from 10:00 PM to 8:00 AM), which can reduce Compute and Database costs by up to ~40%.
- **Use EC2 Spot Instances for the Auto Scaling Group:** The 02 EC2 instances within the ASG can be provisioned as Spot Instances instead of On-Demand. Spot Instances can yield savings of up to 70-90% for scalable compute capacity without modifying the Load Balancing or ASG architecture.
- **Optimize EBS Volume Size:** Instead of allocating 30 GB of EBS gp3 per EC2 instance initially, the size can be reduced to 10-15 GB if the source code and OS do not demand excessive space. Elastic Block Store allows flexible volume expansion later if needed.
