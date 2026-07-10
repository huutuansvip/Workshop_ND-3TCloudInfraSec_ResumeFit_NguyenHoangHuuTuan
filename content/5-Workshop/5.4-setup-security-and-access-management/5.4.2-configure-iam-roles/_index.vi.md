---
title: "Cấu hình IAM Roles"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.4.2. </b> "
---

Cấp quyền ủy quyền an toàn cho các máy chủ EC2 giao tiếp với các dịch vụ AWS khác mà không cần lưu trữ Hard-code Access Key.

1. Truy cập dịch vụ **IAM**, tạo role `ResumeMatching-Backend-Role` để cấp cho máy chủ backend chạy trên EC2.
![Tạo Backend IAM Role](/images/5-Workshop/Tao_Backend_IAM_Role.jpg)
<p align="center"><i>Tạo Backend IAM Role</i></p>

2. Tạo role thứ hai mang tên `ResumeMatching-Worker-Role` dành riêng cho Worker server. Đính kèm các policy AWS Managed như `AmazonSQSFullAccess` và quyền thao tác với S3.
![Tạo Worker IAM Role](/images/5-Workshop/Tao_Worker_IAM_Role.jpg)
<p align="center"><i>Tạo Worker IAM Role</i></p>
