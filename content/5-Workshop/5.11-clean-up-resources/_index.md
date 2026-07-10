---
title: "Clean up resources"
date: 2026-07-09
weight: 11
chapter: false
pre: " <b> 5.11. </b> "
---

After completing the workshop and testing process, to avoid incurring unnecessary storage and infrastructure maintenance costs on AWS, proceed to:

1. Delete the Auto Scaling Group to prevent the system from automatically re-initializing servers, then manually Terminate any remaining EC2 Instances.
2. Delete the Application Load Balancer and Target Group.
3. Delete the RDS Database (uncheck the create final Snapshot feature if data retention is not needed) and the RDS Subnet Group.
4. Delete the NAT Gateway, wait until the status is Deleted then Release the Elastic IPs.
5. Release VPC Endpoints, Route Tables, Internet Gateway, Subnets and finally delete the VPC.
6. Empty all objects in the S3 bucket, then proceed to Delete Bucket.
