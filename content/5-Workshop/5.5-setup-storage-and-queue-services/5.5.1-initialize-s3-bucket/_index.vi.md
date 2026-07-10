---
title: "Khởi tạo S3 Bucket"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.5.1. </b> "
---

1. Chuyển sang dịch vụ **S3**, nhấn **Create bucket** để tạo nơi lưu trữ CV và tài liệu của ứng viên.

![Tạo S3](/images/5-Workshop/Tao_S3.jpg)
<p align="center"><i>Tạo S3</i></p>

![Create Folder S3](/images/5-Workshop/Create_Folder_S3.jpg)
<p align="center"><i>Create Folder S3</i></p>

2. Đặt tên bucket có dạng `resume-matching-storage-[AWS-ACCOUNT-ID]-us-east-1`.

3. Tại tab **Permissions**, tiến hành chỉnh sửa **Cross-origin resource sharing (CORS)**. Thêm nội dung JSON để cấu hình `AllowedMethods` bao gồm: `GET`, `PUT`, `POST` nhằm cho phép ứng dụng web tải file lên bucket.

![Bổ sung CORS S3](/images/5-Workshop/Bo_sung_CORS_S3.jpg)
<p align="center"><i>Bổ sung CORS S3</i></p>
