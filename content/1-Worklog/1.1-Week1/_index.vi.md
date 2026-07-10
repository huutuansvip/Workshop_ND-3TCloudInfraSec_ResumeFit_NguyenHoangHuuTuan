---
title: "Worklog Tuần 1"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---
### Mục tiêu tuần 1:

* Hoàn tất quy trình hội nhập nhân sự mới (onboarding), làm quen các thành viên và quy định làm việc của công ty.
* Thiết lập môi trường phát triển ứng dụng cục bộ (IDE, Git, tài khoản kết nối, SSH key).
* Nghiên cứu lý thuyết cơ bản về Điện toán đám mây và các dịch vụ cốt lõi của AWS.
* Đăng ký tài khoản AWS Free Tier và thiết lập bảo mật tối đa cùng cảnh báo chi phí.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | **Quy trình hội nhập (Onboarding):**<br>- Gặp gỡ đại diện nhân sự và đội ngũ dự án; tiếp nhận thẻ truy cập, tài khoản các kênh liên lạc (Slack, Microsoft Teams) và bảng công việc (Jira).<br>- Đọc và ký cam kết bảo mật (NDA), tìm hiểu quy định nội bộ và tiêu chuẩn làm việc tại phòng IT. | 20/04/2026 | 20/04/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Cấu hình môi trường phát triển cục bộ:**<br>- Cài đặt công cụ soạn thảo mã nguồn VS Code cùng các tiện ích bổ sung cần thiết (GitLens, Markdown All in One, YAML).<br>- Cài đặt Git client (Git Bash) trên máy tính và cấu hình các thông số toàn cục (`user.name`, `user.email`).<br>- Khởi tạo cặp khóa SSH (Public/Private Key) và liên kết khóa công khai lên tài khoản GitHub để đồng bộ mã nguồn bảo mật. | 21/04/2026 | 21/04/2026 | [Git Tutorial for Beginners (YouTube)](https://www.youtube.com/watch?v=RGOj5yH7evk) |
| 4 | - Đăng ký tài khoản AWS Free Tier mới; kích hoạt bảo mật đa nhân tố (MFA) qua ứng dụng Google Authenticator cho tài khoản Root; thiết lập AWS Budgets để gửi email cảnh báo tự động khi hóa đơn vượt quá $1.00 USD. | 22/04/2026 | 22/04/2026 | [AWS Account Setup Guide](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/) |
| 5 | **Nghiên cứu Điện toán đám mây căn bản:**<br>- Học lý thuyết về các mô hình triển khai đám mây (Public, Private, Hybrid) và các mô hình dịch vụ (IaaS, PaaS, SaaS).<br>- Tìm hiểu cấu trúc hạ tầng toàn cầu của AWS gồm Regions (Vùng địa lý), Availability Zones (AZs - Vùng sẵn sàng), Edge Locations, và mạng lưới kết nối.<br>- Nghiên cứu tổng quan về mục đích sử dụng các dịch vụ cốt lõi: EC2 (máy chủ ảo), S3 (lưu trữ), VPC (mạng ảo), RDS (cơ sở dữ liệu). | 23/04/2026 | 24/04/2026 | [AWS Certified Cloud Practitioner Course (YouTube)](https://www.youtube.com/watch?v=3hLmDS159yA) |
| 6 | **Báo cáo tuần và Thực hành Console:**<br>- Soạn thảo văn bản báo cáo giới thiệu công ty, phòng ban thực tập, lập kế hoạch chi tiết mục tiêu thực tập cá nhân và các chỉ số đánh giá hiệu quả (KPIs).<br>- Đăng nhập vào AWS Management Console, thực hành tìm kiếm dịch vụ, chuyển đổi vùng (Region) và làm quen với giao diện quản trị web. | 24/04/2026 | 24/04/2026 | [AWS Console Overview](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/getting-started.html) |

### Kết quả đạt được tuần 1:

* **Hội nhập doanh nghiệp nhanh chóng:** Hoàn thành đầy đủ thủ tục tiếp nhận nhân sự, hiểu rõ văn hóa doanh nghiệp, quy chế bảo mật thông tin và quy trình báo cáo tiến độ công việc hàng ngày của phòng IT.
* **Môi trường làm việc sẵn sàng:** Cấu hình thành công môi trường code cá nhân trên máy tính, đảm bảo đồng bộ mã nguồn qua Git trơn tru và kết nối bảo mật qua SSH.
* **Tài khoản đám mây bảo mật cao:** Đăng ký thành công tài khoản AWS cá nhân có cấu hình bảo mật MFA chặt chẽ cùng hệ thống cảnh báo ngân sách hoạt động chuẩn xác, phòng ngừa chi phí phát sinh ngoài ý muốn.
* **Nắm vững kiến thức nền tảng:** Hiểu rõ bản chất vật lý của hạ tầng đám mây AWS, phân biệt được vùng sẵn sàng (AZ) và vùng địa lý (Region), nắm được vai trò của các dịch vụ Cloud cốt lõi.
* **Hoàn thành báo cáo tuần đầu:** Viết và nộp báo cáo giới thiệu công ty và mục tiêu thực tập đúng thời hạn quy định.