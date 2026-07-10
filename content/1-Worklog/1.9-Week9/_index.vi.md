---
title: "Worklog Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
### Mục tiêu tuần 9:

* Học tập phương pháp quản lý hạ tầng bằng mã (Infrastructure as Code - IaC) và lợi ích đối với vận hành doanh nghiệp.
* Sử dụng thành thạo cấu trúc tệp, biến số, nhà cung cấp (Providers) và file quản lý trạng thái (State File) của Terraform.
* Tự động hóa hoàn toàn quy trình thiết lập mạng ảo và máy chủ ảo trên AWS bằng mã lệnh Terraform.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | **Nghiên cứu hạ tầng dạng mã IaC:**<br>- Tìm hiểu lợi ích của IaC: Khả năng tái tạo môi trường nhanh, tính đồng nhất hệ thống, so sánh lập trình khai báo (Declarative) và mệnh lệnh (Imperative).<br>- Nghiên cứu cú pháp ngôn ngữ cấu hình HCL (HashiCorp Configuration Language) và các mối quan hệ phụ thuộc giữa các tài nguyên. | 15/06/2026 | 15/06/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Cài đặt và Khởi tạo Terraform cục bộ:**<br>- Tải và cấu hình công cụ dòng lệnh Terraform CLI; liên kết quyền định danh tài khoản AWS cục bộ dưới máy tính cá nhân.<br>- Tạo thư mục làm việc, viết tệp tin cấu hình nền tảng và chạy lệnh `terraform init` để tải về các trình điều khiển (Provider plugins) kết nối đến AWS. | 16/06/2026 | 16/06/2026 | [Terraform Course - IaC Tutorial (YouTube)](https://www.youtube.com/watch?v=7xngnjfIlK4) |
| 4 | **Lập trình khai báo hệ thống mạng ảo:**<br>- Soạn thảo các tệp tin cấu hình (`providers.tf`, `variables.tf`, `vpc.tf`) mô tả chi tiết tài nguyên VPC, các phân vùng mạng Public/Private Subnet, Internet Gateway và bảng định tuyến Route Table. | 17/06/2026 | 18/06/2026 | [Terraform AWS Provider Reference](https://registry.terraform.io/providers/hashicorp/aws/latest/docs) |
| 5 | **Viết mã tài nguyên máy chủ compute:**<br>- Lập trình tệp tin `compute.tf` để khai báo máy chủ ảo EC2, ổ đĩa EBS đi kèm, nhóm bảo mật Security Group và liên kết tệp khóa SSH. | 18/06/2026 | 19/06/2026 | [Terraform EC2 Resource Examples](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance) |
| 6 | **Triển khai và kiểm thử dọn dẹp hạ tầng:**<br>- Chạy lệnh `terraform plan` để kiểm tra kế hoạch thay đổi hạ tầng; chạy `terraform apply` thực hiện tạo toàn bộ hạ tầng tự động lên AWS trong vài giây.<br>- Thực hiện kiểm tra trên Console xác thực các tài nguyên đã chạy, sau đó chạy lệnh `terraform destroy` để kiểm thử quy trình thu hồi xóa bỏ sạch sẽ tài nguyên. | 19/06/2026 | 19/06/2026 | [HashiCorp Terraform Tutorial](https://developer.hashicorp.com/terraform/tutorials/aws-get-started) |

### Kết quả đạt được tuần 9:

* **Chuyển đổi số trong quản lý hạ tầng:** Loại bỏ hoàn toàn quy trình click chuột thủ công trên giao diện web bằng việc số hóa hạ tầng thành các tệp mã nguồn tái sử dụng.
* **Lập trình hóa tài nguyên mạng/compute:** Tham số hóa cấu hình hệ thống một cách khoa học thông qua biến số (Variables) và tệp tin xuất đầu ra (Outputs).
* **Khởi tạo hệ thống siêu tốc:** Thiết lập toàn bộ hệ thống mạng VPC phức tạp và máy chủ EC2 chỉ bằng một vài dòng lệnh CLI.
* **Quản lý chặt chẽ trạng thái hạ tầng:** Kiểm soát và đồng bộ hóa lịch sử thay đổi cấu trúc phần cứng hệ thống nhờ tệp tin trạng thái State File của Terraform.