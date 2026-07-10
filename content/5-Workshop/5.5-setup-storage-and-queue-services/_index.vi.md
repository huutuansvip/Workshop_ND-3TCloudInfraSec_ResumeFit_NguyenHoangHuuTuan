---
title: "Thiết lập Dịch vụ Lưu trữ và Hàng đợi"
date: 2026-07-09
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

Để xử lý khối lượng lớn dữ liệu đầu vào và các tác vụ AI phức tạp mà không làm tắc nghẽn hệ thống web, chúng ta cần tách rời luồng dữ liệu. Phần này trình bày cách sử dụng Amazon S3 để tạo kho lưu trữ an toàn, khả năng mở rộng vô hạn dành cho CV và tài liệu của ứng viên. Kế tiếp, chúng ta sẽ thiết lập Amazon SQS - dịch vụ hàng đợi thông điệp - làm cầu nối trung gian giữa máy chủ web (Backend) và máy chủ xử lý nền (Worker). Kiến trúc này giúp ứng dụng web phản hồi nhanh chóng với người dùng trong khi các tác vụ nặng được xếp hàng và xử lý tuần tự, đảm bảo hệ thống không bị quá tải.

### Nội dung chi tiết:

{{% children /%}}
