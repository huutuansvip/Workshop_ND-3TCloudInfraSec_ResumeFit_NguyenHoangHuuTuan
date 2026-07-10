---
title: "Cấu hình AMI và Launch Template"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.8.1. </b> "
---

1. Chuẩn hóa môi trường EC2 vừa cài đặt bằng cách tạo ra một Amazon Machine Image (AMI) mang tên `ResumeMatching-Backend-AMI`.

![Tạo AMIs](/images/5-Workshop/Tao_AMIs.jpg)
<p align="center"><i>Tạo AMIs</i></p>

2. Từ AMI này, tạo một **Launch Template** mang tên `ResumeMatching-LT` chứa các cấu hình phần cứng, mạng và bảo mật chuẩn.

![Tạo launch template](/images/5-Workshop/Tao_launch_template.jpg)
<p align="center"><i>Tạo launch template</i></p>
