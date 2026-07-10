---
title: "Worklog Tuần 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---
### Mục tiêu tuần 3:

* Tìm hiểu các khái niệm cốt lõi về mạng ảo Amazon VPC (Virtual Private Cloud).
* Thiết kế và triển khai mô hình mạng bảo mật bao gồm các phân vùng mạng công cộng (Public Subnet) và mạng nội bộ (Private Subnet).
* Định tuyến lưu lượng thông tin giữa các subnet và bảo mật kết nối nội bộ giữa các máy chủ ảo EC2.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | **Nghiên cứu lý thuyết mạng ảo:**<br>- Học lý thuyết cơ bản về mạng: Địa chỉ IP, dải mạng CIDR, cách chia Subnet (mạng con), bảng định tuyến (Route Tables) và cổng Internet (Internet Gateways).<br>- Phân biệt địa chỉ IP Public và IP Private; tìm hiểu cơ chế chuyển gói tin trong VPC. | 04/05/2026 | 04/05/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Triển khai mạng ảo VPC tùy chỉnh:**<br>- Thiết kế và cấu hình một VPC tùy chỉnh với dải mạng CIDR `10.0.0.0/16`.<br>- Tạo một phân vùng mạng công cộng Public Subnet (`10.0.1.0/24`) và phân vùng mạng nội bộ Private Subnet (`10.0.2.0/24`) trong cùng một Availability Zone để cô lập dữ liệu. | 05/05/2026 | 05/05/2026 | [Hướng dẫn cấu hình AWS VPC (YouTube)](https://www.youtube.com/watch?v=N6qtN0c_e9A) |
| 4 | **Thiết lập cổng định tuyến Internet:**<br>- Tạo mới một cổng Internet Gateway (IGW) và gắn (attach) trực tiếp vào VPC vừa tạo để mở đường kết nối ra ngoài.<br>- Thiết lập bảng định tuyến Public Route Table, thêm dòng cấu hình trỏ mọi IP (`0.0.0.0/0`) đi ra ngoài qua IGW, và gán bảng định tuyến này vào Public Subnet. | 06/05/2026 | 06/05/2026 | [Amazon VPC Route Tables Guide](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html) |
| 5 | **Khởi tạo hệ thống máy chủ và bảo mật:**<br>- Khởi chạy máy chủ ảo EC2 (tượng trưng cho Web server) đặt ở Public Subnet và một máy chủ EC2 (tượng trưng cho Database server) ở Private Subnet.<br>- Thiết lập cấu hình Security Groups cho hai máy chủ; cấu hình luật chỉ cho phép máy chủ Private nhận gói tin từ địa chỉ của máy chủ Public. | 07/05/2026 | 08/05/2026 | [AWS Security Groups Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html) |
| 6 | **Kiểm thử liên kết mạng ảo:**<br>- Thực hiện kết nối SSH vào máy chủ Public EC2, từ terminal này tiếp tục ping/SSH nội bộ tới máy chủ Private EC2 thông qua IP Private (`10.0.2.x`).<br>- Xác nhận máy chủ ở Private Subnet hoàn toàn bị chặn và không thể kết nối trực tiếp từ Internet. | 08/05/2026 | 08/05/2026 | [AWS VPC Troubleshooting Guide](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-troubleshooting.html) |

### Kết quả đạt được tuần 3:

* **Tự tạo lập hạ tầng mạng riêng biệt:** Thiết kế và xây dựng thành công mạng ảo độc lập VPC đáp ứng các yêu cầu phân hoạch IP khoa học.
* **Phân lớp mạng bảo mật:** Triển khai cấu trúc liên mạng an toàn tách biệt máy chủ mặt ngoài và máy chủ lưu trữ dữ liệu phía sau.
* **Quản trị định tuyến thông tin:** Làm chủ kỹ thuật cấu hình đường truyền internet thông qua Internet Gateway và Route Tables.
* **Thiết lập tường lửa an toàn:** Sử dụng nhóm bảo mật Security Group thiết lập bộ lọc kết nối thông minh, ngăn chặn các truy cập trái phép cấp mạng.
* **Kiểm thử máy chủ trung chuyển (Bastion Host):** Xác thực thành công kết nối đa tầng và nguyên lý hoạt động của máy chủ trung chuyển (Jump Box) trong VPC.