---
title: "Worklog Tuần 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---
### Mục tiêu tuần 4:

* Tìm hiểu vòng đời máy chủ ảo Amazon EC2 (Elastic Compute Cloud), các nhóm dòng máy chủ (Families) và Ảnh hệ điều hành (AMIs).
* Triển khai một máy chủ web Nginx hoạt động trên hệ điều hành Linux EC2.
* Cấu hình các quy tắc bảo mật mạng và gán địa chỉ IP tĩnh cố định (Elastic IP).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | **Nghiên cứu hạ tầng EC2:**<br>- Tìm hiểu các nhóm dòng máy chủ EC2 (T chuyên tối ưu chi phí, M chuyên dụng đa năng), tiêu chuẩn cấu hình phần cứng; phân biệt lưu trữ tạm thời Instance Store và ổ đĩa EBS; nắm vững cơ chế xác thực qua Key Pair. | 11/05/2026 | 11/05/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Khởi tạo máy chủ ảo EC2:**<br>- Khởi chạy một thực thể máy chủ ảo `t2.micro` sử dụng AMI Ubuntu Linux đặt trong phân vùng Public Subnet của VPC đã thiết kế.<br>- Cấu hình đĩa lưu trữ dung lượng 20GB loại gp3 EBS; tạo và tải về tệp tin khóa bảo mật riêng tư (.pem) lưu an toàn trên máy tính cá nhân. | 12/05/2026 | 12/05/2026 | [Hướng dẫn host website cá nhân trên AWS EC2 (YouTube)](https://www.youtube.com/watch?v=Islmm-LMu38) |
| 4 | **Cài đặt và cấu hình Web Server:**<br>- Sử dụng giao diện dòng lệnh SSH kết nối an toàn từ máy tính cá nhân tới IP công cộng của EC2.<br>- Cập nhật danh sách gói phần mềm hệ thống (`sudo apt update`) và tiến hành cài đặt dịch vụ máy chủ web Nginx; kiểm tra dịch vụ Nginx khởi chạy thành công. | 13/05/2026 | 13/05/2026 | [Nginx Installation and Setup Guide](https://nginx.org/en/docs/beginners_guide.html) |
| 5 | **Cấu hình bảo mật và Giao diện Web:**<br>- Thay đổi nội dung thư mục web mặc định của Nginx bằng mã nguồn trang HTML giới thiệu thông tin thực tập cá nhân.<br>- Chỉnh sửa nhóm bảo mật (Security Group), mở cổng HTTP (cổng 80) và HTTPS (cổng 443) cho mọi IP truy cập; giới hạn cổng quản trị SSH (22) chỉ cho IP của bạn. | 14/05/2026 | 15/05/2026 | [AWS Security Groups for EC2 Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/working-with-security-groups.html) |
| 6 | **Cố định địa chỉ IP máy chủ:**<br>- Thực hiện yêu cầu cấp phát một địa chỉ IP tĩnh công cộng (Elastic IP) và thực hiện liên kết (associate) trực tiếp vào EC2.<br>- Thực hiện khởi động lại (reboot) máy chủ EC2, truy cập kiểm tra xác nhận địa chỉ IP không bị thay đổi. | 15/05/2026 | 15/05/2026 | [Elastic IP Addresses Reference](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) |

### Kết quả đạt được tuần 4:

* **Thực hành thành thạo AWS Compute:** Nắm vững quy trình cấu hình đĩa cứng, hệ điều hành và thông số CPU/RAM khi khởi tạo thực thể máy chủ ảo.
* **Vận hành hệ thống máy chủ web:** Triển khai thành công dịch vụ Nginx hoạt động ổn định trên môi trường Linux Ubuntu.
* **Cấu hình tường lửa tối ưu:** Bảo vệ thành công máy chủ ảo bằng cách kiểm soát quyền truy cập cổng dịch vụ mặt ngoài và khóa chặt các cổng nhạy cảm.
* **Triển khai địa chỉ mạng tĩnh:** Loại bỏ hoàn toàn sự cố gián đoạn dịch vụ khi restart máy chủ nhờ liên kết Elastic IP.
* **Quản trị hệ thống qua dòng lệnh:** Nâng cao kỹ năng quản lý Linux từ xa thông qua SSH và tương tác với các tiến trình hệ thống.