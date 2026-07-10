---
title: "Worklog Tuần 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---
### Mục tiêu tuần 2:

* Tìm hiểu và ứng dụng các khái niệm về Quản lý truy cập và Định danh (IAM) trên AWS.
* Hiểu về nguyên lý đặc quyền tối thiểu (Least Privilege) và thiết lập bảo mật truy cập.
* Thực hành tạo Người dùng (Users), Nhóm (Groups), Chính sách tùy chỉnh (Custom Policies) và Vai trò (Roles).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | **Nghiên cứu lý thuyết IAM:**<br>- Tìm hiểu sâu về các khái niệm cốt lõi của AWS IAM: Users, Groups, Roles, Policies và cơ chế bảo mật xác thực MFA.<br>- Phân biệt các loại chính sách phân quyền: AWS Managed Policies (AWS quản lý), Customer Managed Policies (Khách hàng tự quản lý) và Inline Policies (Gắn trực tiếp). | 27/04/2026 | 27/04/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Phân quyền và Quản lý nhóm người dùng:**<br>- Tạo mới tài khoản IAM Administrator User để phục vụ quản trị hàng ngày, tránh đăng nhập tài khoản Root.<br>- Khởi tạo các IAM User cho lập trình viên; đưa vào nhóm 'Developers' mới tạo; thiết lập các quy tắc mật khẩu an toàn (độ dài trên 12 ký tự, bắt buộc chứa ký tự đặc biệt) và yêu cầu đổi mật khẩu ở lần đăng nhập đầu tiên. | 28/04/2026 | 28/04/2026 | [Hướng dẫn chi tiết về AWS IAM User (YouTube)](https://www.youtube.com/watch?v=bO25vbkoJlA) |
| 4 | **Lập trình chính sách phân quyền JSON:**<br>- Viết một chính sách phân quyền tùy chỉnh (Custom IAM Policy) bằng ngôn ngữ JSON chỉ cho phép đọc/ghi dữ liệu tại một S3 bucket nhất định và từ chối mọi hoạt động ở bucket khác.<br>- Sử dụng công cụ AWS Policy Simulator để chạy giả lập, xác nhận chính sách hoạt động đúng như mong đợi. | 29/04/2026 | 29/04/2026 | [AWS IAM Policies Reference](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies.html) |
| 5 | **Phân quyền tài nguyên qua IAM Roles:**<br>- Nghiên cứu dịch vụ khóa bảo mật tạm thời AWS STS và vai trò (IAM Roles) dành cho các tài nguyên AWS.<br>- Tạo một IAM Role có quyền đọc dữ liệu từ S3, gắn (attach) Role này vào máy chủ ảo EC2 và kết nối kiểm thử, xác nhận đọc tệp tin từ S3 thành công mà không cần lưu khóa Access Key trên máy chủ. | 30/04/2026 | 01/05/2026 | [IAM Roles for Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html) |
| 6 | **Kiểm toán an toàn thông tin:**<br>- Xuất báo cáo kiểm tra thông tin đăng nhập (IAM Credential Report) để phân tích các rủi ro bảo mật tiềm ẩn (khóa chưa xoay vòng, MFA chưa bật).<br>- Cấu hình các chính sách và tắt các khóa API (Access Key) không còn hoạt động. | 01/05/2026 | 01/05/2026 | [AWS IAM Best Practices Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) |

### Kết quả đạt được tuần 2:

* **Làm chủ hệ thống phân quyền IAM:** Nắm vững cấu trúc phân cấp tài khoản, cơ chế xác thực và cú pháp viết chính sách phân quyền JSON của AWS.
* **Bảo mật tuyệt đối tài khoản Root:** Áp dụng tiêu chuẩn an toàn đám mây bằng cách ngắt sử dụng tài khoản Root và chuyển giao sang tài khoản IAM Admin.
* **Phân quyền chi tiết (Fine-grained Access Control):** Triển khai thành công các chính sách bảo mật tùy chỉnh ngăn chặn rò rỉ dữ liệu ngoài phạm vi công việc.
* **Triển khai ứng dụng không lưu khóa bảo mật:** Sử dụng IAM Role thay thế cho Access Key truyền thống khi kết nối các dịch vụ EC2 và S3, triệt tiêu nguy cơ lộ lọt thông tin.
* **Kiểm toán bảo mật định kỳ:** Thực hiện đánh giá an toàn tài khoản và áp dụng chính sách mật khẩu mạnh cho toàn tổ chức.