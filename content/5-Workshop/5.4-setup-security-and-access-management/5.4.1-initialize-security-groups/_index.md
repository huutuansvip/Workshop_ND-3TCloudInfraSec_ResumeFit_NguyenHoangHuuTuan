---
title: "Initialize Security Groups"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.4.1. </b> "
---

Setup virtual firewalls to control network traffic between resources at the protocol and port level.

1. **ALB Security Group** (`ResumeMatching-ALB-SG`): Open port HTTP (`80`) and HTTPS (`443`) (TCP) with Source as `0.0.0.0/0` to allow users to access the web.
![Create ALB Security Group](/images/5-Workshop/Tao_ALB_Security_Group.jpg)
<p align="center"><i>Create ALB Security Group</i></p>

2. **Backend Security Group** (`ResumeMatching-Backend-SG`): Configure Inbound rule allowing HTTP protocol on TCP port. Source is restricted to only receive traffic from `ResumeMatching-ALB-SG`.
![Create Backend Security Group](/images/5-Workshop/Tao_Backend_Security_Group.jpg)
<p align="center"><i>Create Backend Security Group</i></p>

3. **Worker Security Group** (`ResumeMatching-Worker-SG`): Firewall protecting the Worker Server handling background tasks.
![Create Worker Security Group](/images/5-Workshop/Tạo_Worker_Security_Group.jpg)
<p align="center"><i>Create Worker Security Group</i></p>

4. **Database Security Group** (`ResumeMatching-RDS-SG`): Open port `5432` (PostgreSQL). Source only allows internal connections from Backend and Worker Security Groups.
![Create Database Security Group](/images/5-Workshop/Tao_Database_Security_Group.jpg)
<p align="center"><i>Create Database Security Group</i></p>
