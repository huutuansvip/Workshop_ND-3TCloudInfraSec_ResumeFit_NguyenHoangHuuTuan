---
title: "Worklog Tuần 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---
### Mục tiêu tuần 5:

* Triển khai hệ thống lưu trữ đám mây và cơ sở dữ liệu quan hệ trên AWS.
* Cấu hình dịch vụ Amazon S3 để chạy web tĩnh và lưu trữ tài nguyên đa phương tiện.
* Cấu hình và khởi tạo cơ sở dữ liệu Amazon RDS, kết nối dữ liệu từ máy chủ web EC2.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | **Nghiên cứu lưu trữ và cơ sở dữ liệu:**<br>- Tìm hiểu các phân lớp lưu trữ S3 (S3 Standard, S3 Intelligent-Tiering, S3 Glacier), cơ chế phân quyền S3 bucket; lý thuyết về dịch vụ cơ sở dữ liệu quan hệ RDS, cấu hình đa vùng sẵn sàng (Multi-AZ) và bản sao đọc (Read Replicas). | 18/05/2026 | 18/05/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Tự lưu trữ Web tĩnh trên S3:**<br>- Khởi tạo một S3 Bucket với tên định danh duy nhất; tải lên các tệp tin mã nguồn trang web tĩnh (HTML/CSS/JS).<br>- Thiết lập S3 Bucket Policy cấp quyền đọc công khai (`GetObject`) cho tất cả mọi người và kích hoạt tính năng Static Website Hosting. | 19/05/2026 | 19/05/2026 | [Hosting a Static Website on Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html) |
| 4 | **Khởi tạo cơ sở dữ liệu cô lập RDS:**<br>- Khởi tạo máy chủ cơ sở dữ liệu RDS chạy hệ quản trị MySQL; cấu hình Subnet Group để chỉ định vị trí chạy của RDS nằm trong Private Subnet của VPC.<br>- Thiết lập tài khoản quản trị Admin và lưu thông tin kết nối bảo mật. | 20/05/2026 | 21/05/2026 | [Hướng dẫn kết nối EC2 đến cơ sở dữ liệu private RDS (YouTube)](https://www.youtube.com/watch?v=TRkp54ekyY4) |
| 5 | **Bảo mật cổng dữ liệu (Database Security):**<br>- Thiết lập một nhóm bảo mật riêng cho RDS (Database Security Group); cấu hình luật cho phép nhận kết nối qua cổng MySQL (3306) từ duy nhất nhóm bảo mật (Security Group) của EC2 Web Server. | 21/05/2026 | 22/05/2026 | [AWS RDS Security Group Rules](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_SettingUpAPIs.html#CHAP_SettingUpAPIs.SecurityGroups) |
| 6 | **Kết nối và Truy vấn dữ liệu thực tế:**<br>- Thực hiện kết nối SSH vào máy chủ EC2, tiến hành cài đặt chương trình MySQL Client (`sudo apt install mysql-client`).<br>- Sử dụng dòng lệnh kết nối trực tiếp đến Endpoint của RDS MySQL, tạo mới cơ sở dữ liệu, khởi tạo bảng dữ liệu và thực thi ghi log thử nghiệm thành công. | 22/05/2026 | 22/05/2026 | [Connecting to an Amazon RDS Database Instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html) |

### Kết quả đạt được tuần 5:

* **Tối ưu chi phí chạy Front-end:** Triển khai thành công ứng dụng web tĩnh trực tiếp trên S3 tĩnh giúp giảm tải chi phí xử lý của máy chủ ảo.
* **Bảo vệ hệ cơ sở dữ liệu đám mây:** Cấu hình thành công hệ quản trị dữ liệu RDS MySQL nằm ẩn dưới Private Subnet, tránh rò rỉ thông tin trước các đợt scan cổng từ Internet.
* **Liên kết dữ liệu an toàn:** Áp dụng nguyên lý tường lửa phân lớp liên thông máy chủ - cơ sở dữ liệu qua cấu hình Security Group.
* **Thành thạo kỹ năng thao tác cơ sở dữ liệu:** Nắm vững cách quản trị kết nối từ xa, kiểm tra trạng thái hoạt động và truy vấn dữ liệu từ máy chủ trung gian.