---
title: "Worklog Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---
### Mục tiêu tuần 6:

* Học kiến thức thiết kế hệ thống có tính sẵn sàng cao (High Availability) bằng Auto Scaling và Cân bằng tải (Load Balancer).
* Triển khai bộ cân bằng tải ứng dụng Application Load Balancer (ALB) phân phối lưu lượng người dùng.
* Cấu hình nhóm mở rộng tự động Auto Scaling Group (ASG) tự điều chỉnh số lượng máy chủ dựa theo tải thực tế.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | **Nghiên cứu kiến trúc sẵn sàng cao (HA):**<br>- Nghiên cứu thiết kế hệ thống HA; so sánh cơ chế mở rộng ngang (Horizontal) và mở rộng dọc (Vertical); tìm hiểu cách thức ALB kiểm tra sức khỏe máy chủ (Health Check) và cơ chế co giãn tự động. | 25/05/2026 | 25/05/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Đóng gói Ảnh hệ điều hành máy chủ:**<br>- Dừng tạm thời máy chủ ảo EC2 ở tuần 4 để tránh xung đột dữ liệu đĩa cứng.<br>- Tiến hành tạo một Ảnh đĩa hệ thống tùy chỉnh (Custom AMI) lưu trữ toàn bộ cấu hình Nginx và mã nguồn HTML đang chạy ổn định. | 26/05/2026 | 26/05/2026 | [How to Create an AMI from EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami-ebs.html) |
| 4 | **Thiết lập Nhóm co giãn tự động ASG:**<br>- Tạo một Launch Template (Cấu hình khởi chạy) từ AMI vừa đóng gói; thiết lập các thông số về mạng và nhóm bảo mật cho máy chủ ảo thế hệ sau.<br>- Cấu hình Auto Scaling Group (ASG) trải rộng trên nhiều Subnet khác nhau để dự phòng sự cố (Số lượng tối thiểu: 1, Mong muốn: 2, Tối đa: 4). | 27/05/2026 | 27/05/2026 | [Amazon EC2 Auto Scaling Guide](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html) |
| 5 | **Triển khai bộ cân bằng tải ALB:**<br>- Tạo bộ Application Load Balancer (ALB) đặt trong phân vùng mạng Public Subnets; cấu hình mở cổng 80 tiếp nhận yêu cầu từ người dùng internet.<br>- Định tuyến các yêu cầu kết nối từ ALB trỏ trực tiếp về nhóm Target Group chứa các máy chủ do Auto Scaling Group quản lý. | 28/05/2026 | 29/05/2026 | [Hướng dẫn cấu hình AWS Auto Scaling & Load Balancer (YouTube)](https://www.youtube.com/watch?v=0mwgbiJae5Q) |
| 6 | **Kiểm thử khả năng chịu tải của hệ thống:**<br>- Kết nối SSH vào máy chủ đang chạy, tải công cụ `stress` giả lập đẩy hiệu năng xử lý CPU vượt quá ngưỡng 80%.<br>- Giám sát giao diện điều khiển ASG để xác thực hệ thống tự động khởi chạy máy chủ mới (Scale Out) và tự động tắt máy chủ khi tải giảm (Scale In). | 29/05/2026 | 29/05/2026 | [Testing Auto Scaling Policies](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scale-based-on-demand.html) |

### Kết quả đạt được tuần 6:

* **Xây dựng hạ tầng chịu lỗi (Fault-Tolerant):** Triển khai thành công hệ thống cụm máy chủ ảo phân bố trên nhiều phân vùng mạng, đảm bảo không có điểm lỗi duy nhất (Single Point of Failure).
* **Chuẩn hóa quy trình nhân bản:** Làm chủ phương pháp đóng gói hệ thống qua việc tạo AMI và viết cấu hình Launch Template.
* **Phân phối lưu lượng thông minh:** Cấu hình ALB điều hướng tải chính xác, tự động cô lập máy chủ bị lỗi nhờ tính năng Health Check.
* **Tự động co giãn tài nguyên theo tải:** Tích hợp thành công chính sách tự động co giãn ASG dựa trên chỉ số sử dụng tài nguyên thực tế.
* **Xác thực độ ổn định thực tế:** Kiểm thử thành công kịch bản quá tải đột biến, chứng minh hiệu quả tối ưu chi phí của hạ tầng điện toán đám mây.