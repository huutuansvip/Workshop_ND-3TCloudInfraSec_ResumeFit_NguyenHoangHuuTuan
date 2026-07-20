---
title: "References"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 5.12. </b> "
---

This page consolidates the references used throughout the Resume Fit project.

## 1. Source code and demo

- Project source: [thuanthien-tran/resume-fit](https://github.com/thuanthien-tran/resume-fit)
- Resume Fit demo on AWS: [http://resumematching-alb-1223673352.us-east-1.elb.amazonaws.com](http://resumematching-alb-1223673352.us-east-1.elb.amazonaws.com)

## 2. AWS services used by the project

- [Amazon Virtual Private Cloud (VPC)](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
- [Amazon Elastic Compute Cloud (EC2)](https://docs.aws.amazon.com/ec2/latest/instancetypes/what-is-amazon-ec2.html)
- [Amazon Simple Storage Service (S3)](https://docs.aws.amazon.com/s3/latest/userguide/Welcome.html)
- [Amazon Relational Database Service (RDS)](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html)
- [Elastic Load Balancing (ALB)](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)
- [Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html)
- [Amazon Simple Queue Service (SQS)](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)
- [AWS Identity and Access Management (IAM)](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)

## 3. Cost Breakdown

The table below presents the estimated monthly cost for the Resume Fit architecture, calculated based on the AWS Pricing Calculator.

**Calculation Assumptions:**
- **Region:** US East (N. Virginia) – us-east-1.
- **Operating Hours:** 730 hours/month (equivalent to 24/7).
- **Pricing Model:** AWS On-Demand Pricing (No Reserved Instances or Savings Plans).
- **System Characteristics:** The system is built for demonstration and project defense, so the traffic is extremely low.

### Cost Estimation Table

| No. | AWS Service | Configuration | Quantity | Estimated Monthly Cost (USD) | Notes | Total (USD) |
|:---:|:---|:---|:---:|---:|:---|---:|
| 1 | Amazon VPC | Public Subnet (02), Private App Subnet (02), Private DB Subnet (02), Internet Gateway (01), Security Group | 1 | 0.00 | Free service | 0.00 |
| 2 | NAT Gateway | us-east-1 ($0.045/hour) | 2 | 32.85 | 02 NAT Gateways | 65.70 |
| 3 | Amazon EC2 | t3.micro Linux ($0.0104/hour) | 3 | 7.59 | 01 Backend, 02 Instances in ASG | 22.77 |
| 4 | Amazon EBS | gp3, 30 GB/EC2 ($0.08/GB-month) | 3 | 2.40 | Allocated with EC2 | 7.20 |
| 5 | Auto Scaling Group | Includes Launch Template, AMI | 1 | 0.00 | Free service | 0.00 |
| 6 | Application Load Balancer| Includes Target Group (01) | 1 | 16.43 | LCU cost is negligible | 16.43 |
| 7 | Amazon RDS | db.t3.micro, Single-AZ ($0.017/hour) | 1 | 12.41 | Relational DB storage | 12.41 |
| 8 | Amazon RDS Storage | 20 GB gp3 ($0.115/GB-month) | 1 | 2.30 | RDS storage capacity | 2.30 |
| 9 | Amazon S3 | Standard, 5 GB ($0.023/GB-month) | 1 | 0.12 | Static data storage | 0.12 |
| 10 | Amazon SQS | Standard Queue & DLQ | 2 | 0.00 | Free under 1 million requests | 0.00 |
| 11 | AWS Secrets Manager | 01 Secret | 1 | 0.40 | $0.40/secret/month | 0.40 |
| 12 | Amazon Cognito | Under 50,000 MAU | 1 | 0.00 | Free service | 0.00 |
| 13 | AWS Systems Manager | Session Manager | 1 | 0.00 | Free service | 0.00 |
| 14 | Amazon CloudWatch | Basic Metrics + Logs | 1 | 0.00 | Free service | 0.00 |
| **Total** | | | | | | **127.33** |

### Analysis and Evaluation

**Total Monthly Deployment Cost:**
The estimated total cost to maintain the system running 24/7 is **$127.33/month**.

**Cost Component Analysis:**
The largest expense comes from the **NAT Gateway ($65.70, accounting for 51.6%)**, as the architecture utilizes 02 NAT Gateways deployed for the Private networks. The second largest is the **Compute and Load Balancing group (EC2 and ALB)**, accounting for approximately 30.7% of the total cost. The Database (RDS) cost accounts for about 11.5%. Services related to Storage, Messaging, Security, and Monitoring make up a very small proportion or are completely free.

**Feasibility Evaluation (AWS Credits $200):**
With the AWS Credits limit of **$200**, the maintenance cost of $127.33/month is perfectly suitable and safe. The system can run continuously for about 1.5 months to serve the demonstration and project defense process without exceeding the allowed credit budget.

**Cost Optimization Recommendations:**
To optimize costs without altering the current architecture, the following measures can be applied:
- **Stop Compute services outside usage hours:** Set up AWS Lambda and EventBridge to automatically stop EC2 instances and RDS at night or during idle periods, thereby significantly saving compute costs.
- **Reduce the number of NAT Gateways:** Although a standard architecture requires 02 NAT Gateways for redundancy, for a demo environment, Private Subnets can be configured to route to a single NAT Gateway. This immediately reduces networking costs by 50% (saving ~$32.85/month) while maintaining full functionality.

## 4. Cost and resource cleanup

- [AWS Pricing Calculator](https://calculator.aws/)
- [AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/)
- [AWS Billing and Cost Management](https://docs.aws.amazon.com/cost-management/latest/userguide/what-is-costmanagement.html)
