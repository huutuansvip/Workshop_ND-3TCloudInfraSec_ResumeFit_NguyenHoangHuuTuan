---
title: "Triển khai Compute và Cấu hình Server"
date: 2026-07-09
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

Sau khi hạ tầng cơ sở đã hoàn tất, bước tiếp theo là khởi chạy các máy chủ tính toán để vận hành mã nguồn ứng dụng. Chúng ta sẽ sử dụng dịch vụ Amazon EC2 để tạo ra các máy chủ Backend. Quá trình này bao gồm việc kết nối an toàn vào máy chủ thông qua Systems Manager (không cần mở port SSH 22 ra internet), cài đặt các môi trường cần thiết như Git, Docker, và tải toàn bộ mã nguồn ứng dụng từ kho lưu trữ. Đây là bước đệm quan trọng để đóng gói máy chủ thành một mẫu chuẩn (AMI) dùng cho việc mở rộng tự động sau này.

### Nội dung chi tiết:

{{% children /%}}
