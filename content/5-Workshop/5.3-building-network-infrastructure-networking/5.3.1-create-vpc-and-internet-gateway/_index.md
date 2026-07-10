---
title: "Create VPC and Internet Gateway"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.3.1. </b> "
---

The isolated network infrastructure (VPC) is a solid security foundation for the entire application, allowing full control over network traffic.

1. Access the VPC Console interface, select **Create VPC**.
![Create VPC](/images/5-Workshop/tao_VPC.jpg)
<p align="center"><i>Create VPC</i></p>

2. Initialize a VPC named `ResumeMatching-VPC` and set the `IPv4 CIDR` IP range to `10.0.0.0/16`.

3. Create an Internet Gateway named `ResumeMatching-IGW` to provide an internet connection path for public resources.
![Create Internet Gateway](/images/5-Workshop/Tao_Internet_Gateway.jpg)
<p align="center"><i>Create Internet Gateway</i></p>

4. Attach the newly created Internet Gateway to `ResumeMatching-VPC`.
![Attach to VPC](/images/5-Workshop/Attach_vao_VPC.jpg)
<p align="center"><i>Attach to VPC</i></p>
