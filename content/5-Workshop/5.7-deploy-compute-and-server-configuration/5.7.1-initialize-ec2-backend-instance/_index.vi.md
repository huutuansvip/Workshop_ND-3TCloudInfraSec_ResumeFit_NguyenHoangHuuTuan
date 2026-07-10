---
title: "Khởi tạo EC2 Backend Instance"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.7.1. </b> "
---

1. Tạo một khóa **Key Pair** (`ResumeMatching-Key`) kiểu RSA.

![Tạo Key Pair](/images/5-Workshop/Tao_Key_Pair.jpg)
<p align="center"><i>Tạo Key Pair</i></p>

2. Tại EC2 Dashboard, khởi chạy một Instance có tên `ResumeMatching-Backend` với Instance type là `t3.micro` đặt trong VPC ứng dụng.

![Tạo EC2 Backend](/images/5-Workshop/Tao_EC2_Backend.jpg)
<p align="center"><i>Tạo EC2 Backend</i></p>

3. Đợi trạng thái Instance chuyển sang `Running` và Status check hiển thị `2/2 checks passed`.
