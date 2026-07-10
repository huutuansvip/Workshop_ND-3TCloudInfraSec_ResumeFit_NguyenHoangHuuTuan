---
title: "Configure IAM Roles"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.4.2. </b> "
---

Safely authorize EC2 servers to communicate with other AWS services without storing Hard-coded Access Keys.

1. Access the **IAM** service, create a role `ResumeMatching-Backend-Role` to grant to the backend server running on EC2.
![Create Backend IAM Role](/images/5-Workshop/Tao_Backend_IAM_Role.jpg)
<p align="center"><i>Create Backend IAM Role</i></p>

2. Create a second role named `ResumeMatching-Worker-Role` dedicated to the Worker server. Attach AWS Managed policies like `AmazonSQSFullAccess` and S3 manipulation rights.
![Create Worker IAM Role](/images/5-Workshop/Tao_Worker_IAM_Role.jpg)
<p align="center"><i>Create Worker IAM Role</i></p>
