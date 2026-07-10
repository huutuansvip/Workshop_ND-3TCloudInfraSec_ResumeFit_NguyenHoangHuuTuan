---
title: "Thiết lập Hệ Quản Trị Cơ Sở Dữ Liệu (RDS)"
date: 2026-07-09
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

Dữ liệu ứng viên, lịch sử đánh giá và thông tin tài khoản cần được lưu trữ có cấu trúc và an toàn tuyệt đối. Trong phần này, chúng ta sẽ triển khai cơ sở dữ liệu quan hệ Amazon RDS với engine PostgreSQL. Việc đặt Database nằm sâu trong Private Subnet giúp dữ liệu hoàn toàn cách ly khỏi Internet. Hơn nữa, để tránh việc lộ mật khẩu cơ sở dữ liệu trong mã nguồn, chúng ta sẽ sử dụng AWS Secrets Manager để mã hóa và quản lý tập trung toàn bộ các thông tin nhạy cảm (như mật khẩu DB, API Key của OpenAI), giúp việc truy xuất trở nên an toàn và dễ dàng xoay vòng mật khẩu khi cần thiết.

### Nội dung chi tiết:

{{% children /%}}
