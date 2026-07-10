---
title: "Worklog Tuần 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---
### Mục tiêu tuần 7:

* Tìm hiểu khả năng giám sát hệ thống và tối ưu hóa tài nguyên bằng Amazon CloudWatch.
* Thiết kế bảng quản trị giám sát (Dashboards) hiển thị các thông số hiệu năng quan trọng (CPU, Memory, Network).
* Thiết lập dịch vụ gửi thông báo Amazon SNS (Simple Notification Service) kết hợp với các bộ cảnh báo tự động (Alarms).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | **Nghiên cứu lý thuyết Giám sát hệ thống:**<br>- Tìm hiểu các thành phần cốt lõi của Amazon CloudWatch: Chỉ số đo lường (Metrics), Chiều đo (Dimensions), Nhóm nhật ký (Log Groups) và Bộ cảnh báo (Alarms).<br>- Tìm hiểu sự khác biệt giữa các chỉ số mặc định của phần cứng và các chỉ số đo lường tùy biến (Custom Metrics). | 01/06/2026 | 01/06/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Thiết kế bảng giám sát hiệu năng Dashboard:**<br>- Khởi tạo giao diện CloudWatch Dashboard riêng biệt; thiết lập cấu hình các đồ thị hiển thị theo thời gian thực về: Tỷ lệ dùng CPU máy chủ, Lưu lượng mạng In/Out của EC2 và Thời gian phản hồi Target Response Time của bộ cân bằng tải ALB. | 02/06/2026 | 02/06/2026 | [Khái niệm cốt lõi về AWS CloudWatch Logs (YouTube)](https://www.youtube.com/watch?v=HRJnhzSSFtk) |
| 4 | **Thiết lập kênh gửi tin thông báo tự động:**<br>- Tạo một Topic phân phối tin nhắn trên dịch vụ Amazon SNS (Simple Notification Service).<br>- Tạo cổng liên kết (Subscription) sử dụng hòm thư điện tử cá nhân trỏ vào Topic; truy cập hòm thư bấm liên kết xác thực do hệ thống AWS gửi về để kích hoạt. | 03/06/2026 | 03/06/2026 | [Amazon SNS Developer Guide](https://docs.aws.amazon.com/sns/latest/dg/welcome.html) |
| 5 | **Cấu hình bộ phát hiện cảnh báo quá tải:**<br>- Thiết lập quy tắc cảnh báo (CloudWatch Alarm) liên kết với tài nguyên máy chủ EC2.<br>- Cấu hình điều kiện kích hoạt: Chuyển sang trạng thái ALARM khi lượng tiêu thụ CPU vượt qua mức 75% duy trì liên tục trong thời gian 2 phút. | 04/06/2026 | 05/06/2026 | [Create a CloudWatch Alarm Based on Static Thresholds](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/ConsoleAlarms.html) |
| 6 | **Xác thực quy trình báo lỗi tự động:**<br>- Chạy ứng dụng đẩy tải xử lý CPU trên máy chủ lên cao.<br>- Theo dõi trạng thái của cảnh báo trên màn hình điều khiển chuyển từ OK sang ALARM; kiểm tra hòm thư cá nhân để xác nhận nhận được thư cảnh báo tự động từ AWS SNS. | 05/06/2026 | 05/06/2026 | [Amazon CloudWatch Troubleshooting Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmTroubleshooting.html) |

### Kết quả đạt được tuần 7:

* **Làm chủ kỹ thuật giám sát điện toán:** Triển khai thành công hạ tầng quan trắc đo lường sức khỏe toàn hệ thống bằng CloudWatch.
* **Xây dựng trung tâm theo dõi trực quan:** Thiết kế Dashboard hiển thị tập trung các biểu đồ phần cứng quan trọng, hỗ trợ xử lý sự cố nhanh chóng.
* **Tự động hóa thông báo khẩn:** Xây dựng thành công kênh phân phối thư cảnh báo tự động qua tích hợp dịch vụ SNS.
* **Phát hiện lỗi chủ động:** Thiết lập chính xác ngưỡng cảnh báo, phát hiện sớm các dấu hiệu quá tải máy chủ trước khi xảy ra sập dịch vụ.
* **Thử nghiệm thành công quy trình khép kín:** Xác thực hoạt động đồng bộ giữa CloudWatch, Alarm và SNS trong kịch bản thực tế.