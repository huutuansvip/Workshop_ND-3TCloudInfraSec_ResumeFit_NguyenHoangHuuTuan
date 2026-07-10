---
title: "Worklog Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---
### Mục tiêu tuần 8:

* Tìm hiểu các nguyên tắc Tích hợp liên tục và Triển khai liên tục (CI/CD).
* Thiết kế và xây dựng các quy trình tự động hóa kiểm thử, biên dịch và triển khai ứng dụng bằng GitHub Actions.
* Tích hợp an toàn tài khoản AWS với GitHub để tự động cập nhật mã nguồn dự án lên S3.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | **Nghiên cứu kiến thức CI/CD:**<br>- Tìm hiểu lý thuyết về tích hợp liên tục (Continuous Integration), triển khai liên tục (Continuous Deployment); so sánh hệ thống GitHub Actions với bộ dịch vụ quản lý mã nguồn gốc của AWS (AWS CodePipeline, AWS CodeBuild, AWS CodeDeploy). | 08/06/2026 | 08/06/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Cấu hình lưu trữ mã nguồn trực tuyến:**<br>- Khởi tạo kho lưu trữ mã nguồn mới trên GitHub (GitHub Repository).<br>- Thực hiện đồng bộ mã nguồn trang web tĩnh từ thư mục cục bộ dưới máy tính lên GitHub qua các câu lệnh Git (`git init`, `git remote add`, `git push`). | 09/06/2026 | 09/06/2026 | [Hướng dẫn cấu hình CI/CD tự động deploy lên AWS ECS (YouTube)](https://www.youtube.com/watch?v=gfCkScWWTvk) |
| 4 | **Cấu hình xác thực an toàn OIDC:**<br>- Cấu hình liên kết định danh OpenID Connect (OIDC) trên AWS IAM, cấu hình tin cậy (Trust relationship) với nhà cung cấp GitHub.<br>- Tạo một IAM Role cấp quyền ghi vào S3 bucket và chỉ cho phép máy chủ của GitHub Actions sử dụng Role này khi chạy deploy. | 10/06/2026 | 11/06/2026 | [AWS OIDC with GitHub Actions Guide](https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services) |
| 5 | **Lập trình tệp cấu hình quy trình Deploy:**<br>- Viết mã cấu hình tệp tin YAML (`.github/workflows/deploy.yml`) định nghĩa các bước: Lấy mã nguồn (Checkout), xác thực tài khoản qua OIDC Role, cài đặt cấu hình AWS credentials và đồng bộ hóa thư mục web lên S3. | 11/06/2026 | 12/06/2026 | [AWS S3 Actions Integration Reference](https://github.com/aws-actions/configure-aws-credentials) |
| 6 | **Vận hành thử nghiệm đường ống tự động:**<br>- Tiến hành chỉnh sửa giao diện web dưới máy tính cá nhân, thực hiện commit và push mã nguồn lên nhánh `main`.<br>- Quan sát giao diện chạy tự động của GitHub Actions runner, đọc lịch sử chạy và kiểm tra trang web S3 để xác nhận website đã tự động cập nhật. | 12/06/2026 | 12/06/2026 | [GitHub Actions Documentation](https://docs.github.com/en/actions) |

### Kết quả đạt được tuần 8:

* **Tự động hóa hoàn toàn quy trình bàn giao code:** Xây dựng thành công hệ thống tự động deploy (Continuous CD), loại bỏ thao tác thủ công phức tạp.
* **Bảo vệ tài khoản Cloud tuyệt đối:** Ứng dụng thành công cơ chế xác thực OIDC không sử dụng Access/Secret Key tĩnh giúp giảm thiểu rủi ro bảo mật.
* **Rút ngắn thời gian triển khai:** Hệ thống tự động biên dịch và tải tài nguyên lên S3 chỉ trong vài giây sau khi có thay đổi trên mã nguồn Git.
* **Tích lũy kinh nghiệm thực tế DevOps:** Thành thạo quy trình làm việc chuyên nghiệp với Git, viết tệp YAML cấu hình pipeline và phân tích log lỗi khi deploy thất bại.