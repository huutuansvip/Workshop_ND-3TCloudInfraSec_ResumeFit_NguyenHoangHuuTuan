---
title: "Initialize EC2 Backend Instance"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.7.1. </b> "
---

1. Create an RSA type **Key Pair** (`ResumeMatching-Key`).
![Create Key Pair](/images/5-Workshop/Tao_Key_Pair.jpg)
<p align="center"><i>Create Key Pair</i></p>

2. At the EC2 Dashboard, launch an Instance named `ResumeMatching-Backend` with Instance type `t3.micro` placed in the application VPC.
![Create EC2 Backend](/images/5-Workshop/Tao_EC2_Backend.jpg)
<p align="center"><i>Create EC2 Backend</i></p>

3. Wait for the Instance state to change to `Running` and Status check to display `2/2 checks passed`.
