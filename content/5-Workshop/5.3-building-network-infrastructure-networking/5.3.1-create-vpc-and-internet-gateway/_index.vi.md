---
title: "Tạo VPC và Internet Gateway"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.3.1. </b> "
---

Hạ tầng mạng cô lập (VPC) là nền tảng bảo mật vững chắc cho toàn bộ ứng dụng, giúp kiểm soát hoàn toàn luồng giao thông mạng.

1. Truy cập vào giao diện VPC Console, chọn **Create VPC**.
![Tạo VPC](/images/5-Workshop/tao_VPC.jpg)
<p align="center"><i>Tạo VPC</i></p>

2. Khởi tạo một VPC với tên `ResumeMatching-VPC` và thiết lập dải IP `IPv4 CIDR` là `10.0.0.0/16`.

3. Bật tính năng **Enable DNS hostnames** cho VPC vừa tạo để hỗ trợ phân giải tên miền.
![Enable DNS Hostnames](/images/5-Workshop/Enable_DNS_Hostnames.jpg)
<p align="center"><i>Enable DNS Hostnames</i></p>

4. Tạo một Internet Gateway có tên `ResumeMatching-IGW` để cung cấp đường truyền kết nối ra internet cho các tài nguyên công khai.
![Tạo Internet Gateway](/images/5-Workshop/Tao_Internet_Gateway.jpg)
<p align="center"><i>Tạo Internet Gateway</i></p>

5. Thực hiện Attach Internet Gateway vừa tạo vào `ResumeMatching-VPC`.
![Attach vào VPC](/images/5-Workshop/Attach_vao_VPC.jpg)
<p align="center"><i>Attach vào VPC</i></p>
