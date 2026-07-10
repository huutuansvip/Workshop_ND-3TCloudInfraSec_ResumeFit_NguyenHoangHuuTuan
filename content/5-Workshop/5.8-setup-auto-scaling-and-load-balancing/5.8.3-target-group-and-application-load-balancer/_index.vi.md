---
title: "Target Group và Application Load Balancer"
date: 2026-07-09
weight: 3
chapter: false
pre: " <b> 5.8.3. </b> "
---

1. Tạo một **Target Group** tên `ResumeMatching-TG`, dạng `Instance` giao thức HTTP trên cổng `8080` (hoặc `80` tùy cấu hình container nội bộ).
![Tạo target group](/images/5-Workshop/Tao_target_group.jpg)
<p align="center"><i>Tạo target group</i></p>

2. Khởi tạo **Application Load Balancer (ALB)** tên `ResumeMatching-ALB`. Lựa chọn Scheme là `Internet-facing` để nhận traffic từ ngoài internet, lắng nghe tại 2 Availability Zones và định tuyến giao thông vào mạng thông qua Target Group trên.
![Tạo ALB](/images/5-Workshop/Tao_ALB.jpg)
<p align="center"><i>Tạo ALB</i></p>
