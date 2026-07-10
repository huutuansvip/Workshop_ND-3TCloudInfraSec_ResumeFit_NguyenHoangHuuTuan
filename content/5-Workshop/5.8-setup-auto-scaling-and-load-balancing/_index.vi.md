---
title: "Thiết lập Tự động mở rộng và Cân bằng tải"
date: 2026-07-09
weight: 8
chapter: false
pre: " <b> 5.8. </b> "
---

Một hệ thống hiện đại phải có khả năng tự động thích ứng với lượng truy cập thay đổi liên tục. Phần này hướng dẫn bạn cách thiết lập cơ chế Tự động mở rộng (Auto Scaling) kết hợp với Cân bằng tải (Load Balancing). Từ máy chủ EC2 đã cài đặt hoàn chỉnh ở bước trước, chúng ta sẽ tạo ra một bản sao lưu (AMI) và cấu hình Launch Template. Auto Scaling Group sẽ dựa vào đó để linh hoạt tự động thêm hoặc bớt máy chủ tùy theo tải thực tế. Phía trước các máy chủ này, một Application Load Balancer (ALB) sẽ đứng ra làm nhiệm vụ đón luồng truy cập từ người dùng và phân bổ thông minh, đồng đều đến các máy chủ đang hoạt động (Healthy).

### Nội dung chi tiết:

{{% children /%}}
