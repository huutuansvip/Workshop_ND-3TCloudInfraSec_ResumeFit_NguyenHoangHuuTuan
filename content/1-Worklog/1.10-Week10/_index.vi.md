---
title: "Worklog Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
### Mục tiêu tuần 10:

* Tìm hiểu mô hình điện toán không máy chủ (Serverless Architecture) và lập trình hướng sự kiện (Event-driven execution).
* Lập trình và khởi chạy hàm chức năng tự động AWS Lambda.
* Thiết lập cổng kết nối API Gateway để định tuyến các yêu cầu gọi hàm từ người dùng ngoài Internet.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | **Nghiên cứu lý thuyết Serverless:**<br>- Tìm hiểu các nguyên lý tính toán hướng sự kiện, cách định phí dựa trên thời gian chạy thực tế; phân tích nguyên nhân và cách khắc phục lỗi khởi động lạnh (Cold Start); nắm rõ vai trò thực thi (Execution Role) cấp quyền bảo mật cho hàm. | 22/06/2026 | 22/06/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Lập trình hàm xử lý AWS Lambda:**<br>- Viết mã nguồn một hàm AWS Lambda bằng ngôn ngữ Python để bóc tách tham số JSON đầu vào, xử lý tính toán logic cơ bản và trả về kết quả định dạng JSON phản hồi chuẩn. | 23/06/2026 | 23/06/2026 | [AWS Lambda & API Gateway Tutorial (YouTube)](https://www.youtube.com/watch?v=eOBq__h4OJ4) |
| 4 | **Triển khai API Gateway định tuyến:**<br>- Khởi tạo cổng kết nối API Gateway (loại HTTP API); thiết lập các phương thức định tuyến (`GET`, `POST`) trỏ về kích hoạt hàm Lambda; cấu hình chính sách chia sẻ tài nguyên CORS để cho phép các trang web bên ngoài gửi yêu cầu. | 24/06/2026 | 24/06/2026 | [Amazon API Gateway Developer Guide](https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html) |
| 5 | **Kiểm thử liên kết hệ thống API:**<br>- Sử dụng chương trình Postman hoặc lệnh curl gửi thử nghiệm các yêu cầu chứa dữ liệu mẫu đến Endpoint API công cộng vừa tạo.<br>- Phân tích nhật ký hoạt động (CloudWatch Logs) để giám sát hiệu năng chạy của hàm Lambda và xử lý các lỗi runtime. | 25/06/2026 | 25/06/2026 | [Testing REST APIs in API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-test-method.html) |
| 6 | **Tích hợp cơ sở dữ liệu Serverless:**<br>- Tạo bảng cơ sở dữ liệu phi quan hệ Amazon DynamoDB; cấu hình thêm quyền ghi tệp cho IAM Role của Lambda.<br>- Sửa đổi mã nguồn Lambda để tự động ghi log thông tin các lượt gọi API thành công vào bảng DynamoDB. | 26/06/2026 | 26/06/2026 | [AWS Serverless Applications Developer Guide](https://docs.aws.amazon.com/serverless/latest/developerguide/what-is-serverless.html) |

### Kết quả đạt được tuần 10:

* **Làm chủ kỹ thuật Serverless:** Triển khai thành công các chương trình logic backend hướng sự kiện, triệt tiêu hoàn toàn công sức cài đặt, cập nhật bản vá hệ điều hành máy chủ.
* **Xây dựng cổng giao tiếp API chuyên nghiệp:** Cấu hình cổng kết nối API Gateway an toàn, phân luồng truy cập và kiểm soát CORS hiệu quả.
* **Debug mã nguồn đám mây thành thạo:** Sử dụng CloudWatch Logs kiểm tra lịch sử in log, đo lường thời gian trễ xử lý của các đoạn code Serverless.
* **Lưu trữ dữ liệu phi cấu trúc không máy chủ:** Tích hợp thành công cơ sở dữ liệu DynamoDB có khả năng tự động mở rộng theo lưu lượng truy cập, duy trì tốc độ đọc ghi dữ liệu cực nhanh.