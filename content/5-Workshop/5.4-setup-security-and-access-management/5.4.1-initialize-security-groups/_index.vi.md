---
title: "Khởi tạo Security Groups"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.4.1. </b> "
---

Thiết lập tường lửa ảo kiểm soát luồng giao thông mạng giữa các tài nguyên ở mức độ giao thức và cổng kết nối.

1. **ALB Security Group** (`ResumeMatching-ALB-SG`): Mở port HTTP (`80`) và HTTPS (`443`) (TCP) với Source là `0.0.0.0/0` để cho phép người dùng truy cập web.

![Tạo ALB Security Group](/images/5-Workshop/Tao_ALB_Security_Group.jpg)
<p align="center"><i>Tạo ALB Security Group</i></p>

2. **Backend Security Group** (`ResumeMatching-Backend-SG`): Cấu hình Inbound rule cho phép giao thức HTTP trên cổng TCP. Source được giới hạn chỉ nhận luồng từ `ResumeMatching-ALB-SG`.

![Tạo Backend Security Group](/images/5-Workshop/Tao_Backend_Security_Group.jpg)
<p align="center"><i>Tạo Backend Security Group</i></p>

3. **Worker Security Group** (`ResumeMatching-Worker-SG`): Tường lửa bảo vệ Worker Server xử lý tác vụ nền.

![Tạo Worker Security Group](/images/5-Workshop/Tạo_Worker_Security_Group.jpg)
<p align="center"><i>Tạo Worker Security Group</i></p>

4. **Database Security Group** (`ResumeMatching-RDS-SG`): Mở port `5432` (PostgreSQL). Source chỉ cho phép nhận kết nối nội bộ từ Backend và Worker Security Group.

![Tạo Database Security Group](/images/5-Workshop/Tao_Database_Security_Group.jpg)
<p align="center"><i>Tạo Database Security Group</i></p>
