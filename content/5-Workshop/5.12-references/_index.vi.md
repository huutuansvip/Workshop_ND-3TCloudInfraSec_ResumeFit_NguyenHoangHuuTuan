---
title: "3. Cost Breakdown"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 5.12. </b> "
---

Báo cáo chi phí dưới đây được lập dựa trên **AWS Pricing Calculator**, ước tính cho việc triển khai hệ thống tại khu vực **US East (N. Virginia) – us-east-1**, sử dụng biểu giá **AWS On-Demand** với thời gian vận hành **730 giờ/tháng (24/7)**. Hệ thống được thiết kế tối giản nhằm phục vụ mục đích demo và chấm điểm đồ án, do đó lưu lượng truy cập dự kiến ở mức rất thấp. Báo cáo không áp dụng các chương trình tối ưu chi phí dài hạn như Reserved Instance hay Savings Plans.

### Bảng Dự Tính Chi Phí Triển Khai (Monthly)

| STT | AWS Service | Configuration | Quantity | Estimated Monthly Cost (USD) | Notes | Total (USD) |
|---|---|---|---|---|---|---|
| 1 | Amazon VPC | 01 VPC, 01 IGW, 02 Public Subnets, 04 Private Subnets, Route Tables | 1 | 0.00 | Dịch vụ định tuyến và phân vùng mạng cơ bản không tính phí. | 0.00 |
| 2 | AWS Security Group | Các quy tắc tường lửa bảo vệ các tài nguyên | 1 | 0.00 | Tính năng bảo mật đi kèm miễn phí. | 0.00 |
| 3 | NAT Gateway | Xử lý lưu lượng từ Private Subnet ra Internet (~1 GB data) | 2 | 32.85 | 0.045 USD/giờ * 730 giờ + 0.045 USD/GB | 65.70 |
| 4 | Amazon EC2 | t3.micro (Linux), On-Demand | 3 | 7.59 | 0.0104 USD/giờ * 730 giờ | 22.78 |
| 5 | Amazon EBS | gp3, 30 GB/volume | 3 | 2.40 | 0.08 USD/GB-tháng | 7.20 |
| 6 | Auto Scaling Group | 01 Launch Template, 01 ASG | 1 | 0.00 | Dịch vụ Auto Scaling miễn phí (chỉ tính phí tài nguyên EC2/EBS tạo ra). | 0.00 |
| 7 | Application Load Balancer | 01 ALB, 01 Target Group (Ước tính < 1 LCU) | 1 | 22.27 | 0.0225 USD/giờ (16.43 USD) + phí LCU cơ bản. | 22.27 |
| 8 | Amazon RDS | Single-AZ, db.t3.micro, 20 GB gp3 | 1 | 14.71 | Instance: 12.41 USD (0.017 USD/giờ), Storage: 2.30 USD | 14.71 |
| 9 | Amazon S3 | Standard Storage (5 GB) | 1 | 0.12 | 0.023 USD/GB-tháng | 0.12 |
| 10 | Amazon SQS | Standard Queue & DLQ (< 1 triệu requests) | 1 | 0.00 | Nằm trong giới hạn Free Tier. | 0.00 |
| 11 | AWS Secrets Manager | 01 Secret (< 10,000 API calls) | 1 | 0.40 | 0.40 USD/secret/tháng | 0.40 |
| 12 | Amazon Cognito | Quản lý người dùng (< 50,000 MAU) | 1 | 0.00 | Nằm trong giới hạn Free Tier (dưới 50,000 MAU). | 0.00 |
| 13 | Amazon CloudWatch | Metrics & Logs cơ bản (< 5 GB) | 1 | 0.00 | Nằm trong giới hạn Free Tier. | 0.00 |
| 14 | AWS Systems Manager | Session Manager (quản lý truy cập an toàn) | 1 | 0.00 | Tính năng kết nối đi kèm miễn phí. | 0.00 |

### Phân Tích Tổng Chi Phí

**1. Tổng chi phí triển khai mỗi tháng:**
Dựa trên bảng ước tính, tổng chi phí để duy trì hệ thống chạy 24/7 trong một tháng là **133.18 USD**.

**2. Phân tích dịch vụ chiếm tỷ trọng chi phí cao nhất:**
- **NAT Gateway** là dịch vụ tiêu tốn nhiều chi phí nhất, chiếm khoảng **49.3%** tổng chi phí (65.70 USD). Việc triển khai 02 NAT Gateways nhằm đảm bảo tính sẵn sàng cao (High Availability) cho các Private Subnets ở 2 Availability Zones khác nhau đã làm tăng đáng kể chi phí cố định (hourly charge).
- **Compute (EC2 & ALB)** là nhóm chi phí lớn thứ hai. Application Load Balancer (22.27 USD) và 3 instances EC2 t3.micro (22.78 USD) phục vụ cho Web/App servers chiếm tỷ trọng đáng kể do yêu cầu duy trì liên tục để nhận traffic.

**3. Đánh giá tính phù hợp với giới hạn AWS Credits (200 USD):**
Tổng chi phí ước tính là **133.18 USD/tháng**, hoàn toàn nằm trong phạm vi giới hạn AWS Credits 200 USD. Hệ thống đáp ứng tốt mục tiêu chạy demo và chấm đồ án trong thời gian 1 tháng mà không gây rủi ro vượt ngân sách. Tuy nhiên, nếu thời gian chấm đồ án kéo dài hơn 1.5 tháng, ngân sách sẽ bị cạn kiệt.

**4. Đề xuất các biện pháp tối ưu chi phí (Giữ nguyên kiến trúc):**
Mặc dù hệ thống đã đáp ứng ngân sách 200 USD, các phương pháp sau có thể được áp dụng để tối ưu thêm chi phí mà không làm thay đổi thiết kế kiến trúc hiện tại:
- **Tối ưu thời gian hoạt động (Start/Stop Scheduling):** Hệ thống chỉ phục vụ demo, do đó không nhất thiết phải hoạt động 24/7. Có thể cấu hình EventBridge hoặc AWS Lambda để tự động tắt EC2 instances và RDS vào ban đêm (ví dụ: tắt từ 22h00 đến 08h00), giúp giảm đến ~40% chi phí Compute và Database.
- **Sử dụng EC2 Spot Instances cho Auto Scaling Group:** 02 EC2 instances nằm trong ASG có thể được thay thế bằng Spot Instances thay vì On-Demand. Spot Instances có thể giúp tiết kiệm lên đến 70-90% chi phí cho phần Compute mở rộng mà vẫn không làm thay đổi kiến trúc Load Balancing hay ASG.
- **Tối ưu dung lượng EBS:** Thay vì cấp phát 30 GB EBS gp3 cho mỗi EC2 instance ngay từ đầu, có thể giảm xuống 10-15 GB nếu source code và hệ điều hành không yêu cầu quá lớn. Tính năng Elastic Block Store cho phép mở rộng dung lượng linh hoạt khi cần thiết.
