---
title: "Target Group and Application Load Balancer"
date: 2026-07-09
weight: 3
chapter: false
pre: " <b> 5.8.3. </b> "
---

1. Create a **Target Group** named `ResumeMatching-TG`, `Instance` type, HTTP protocol on port `8080` (or `80` depending on internal container configuration).

![Create target group](/images/5-Workshop/Tao_target_group.jpg)
<p align="center"><i>Create target group</i></p>

2. Initialize **Application Load Balancer (ALB)** named `ResumeMatching-ALB`. Select Scheme as `Internet-facing` to receive traffic from the external internet, listening on 2 Availability Zones and routing traffic into the network via the above Target Group.

![Create ALB](/images/5-Workshop/Tao_ALB.jpg)
<p align="center"><i>Create ALB</i></p>
