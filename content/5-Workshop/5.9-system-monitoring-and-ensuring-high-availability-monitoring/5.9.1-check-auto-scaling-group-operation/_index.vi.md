---
title: "Kiểm tra hoạt động của Auto Scaling Group"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.9.1. </b> "
---

1. Truy cập dịch vụ **EC2**, điều hướng đến menu **Instances**.
2. Quan sát hệ thống tự động khởi tạo các EC2 mới có tên `ResumeMatching-ASG-Instance` phân bổ đều ở các Availability Zone khác nhau.
3. Một số máy chủ cũ có thể hiển thị trạng thái `Terminated`. Đây là minh chứng ASG đang hoạt động chính xác: tự động thu hồi máy chủ cũ và khởi chạy máy chủ mới khi có sự thay đổi cấu hình hoặc lỗi hệ thống.
