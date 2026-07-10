---
title: "Cấu hình Secrets Manager"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.6.1. </b> "
---

1. Truy cập **AWS Secrets Manager**, tạo secret tên `ResumeMatching-Secrets` để lưu trữ thông tin nhạy cảm.
![Tạo Secret](/images/5-Workshop/Tao_Secret.jpg)
<p align="center"><i>Tạo Secret</i></p>

2. Cấu hình phần **Secret value** với các trường Key/value như `HOST`, `PORT` (`5432`), `USERNAME`, `PASSWORD`, và `OPENAI_API_KEY` của ứng dụng.
![Cập nhật Secrets manager](/images/5-Workshop/Cap_nhat_Secrets_manager.jpg)
<p align="center"><i>Cập nhật Secrets manager</i></p>
