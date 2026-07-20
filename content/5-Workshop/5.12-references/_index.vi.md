---
title: "Tài liệu tham khảo"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 5.12. </b> "
---

Trang này tổng hợp các tài liệu tham khảo được sử dụng trong suốt dự án Resume Fit.

## 1. Source code and demo

- Project source: [thuanthien-tran/resume-fit](https://github.com/thuanthien-tran/resume-fit)
- Resume Fit demo on AWS: [http://resumematching-alb-1223673352.us-east-1.elb.amazonaws.com](http://resumematching-alb-1223673352.us-east-1.elb.amazonaws.com)

## 2. AWS services used by the project

- [Amazon Virtual Private Cloud (VPC)](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
- [Amazon Elastic Compute Cloud (EC2)](https://docs.aws.amazon.com/ec2/latest/instancetypes/what-is-amazon-ec2.html)
- [Amazon Simple Storage Service (S3)](https://docs.aws.amazon.com/s3/latest/userguide/Welcome.html)
- [Amazon Relational Database Service (RDS)](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html)
- [Elastic Load Balancing (ALB)](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)
- [Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html)
- [Amazon Simple Queue Service (SQS)](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)
- [AWS Identity and Access Management (IAM)](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)

## 3. Cost Breakdown

Bảng dưới đây trình bày dự toán chi phí hàng tháng cho hệ thống, được tính toán dựa trên AWS Pricing Calculator.

**Giả định tính toán:**
- **Khu vực (Region):** US East (N. Virginia) – us-east-1.
- **Thời gian vận hành:** 730 giờ/tháng (24/7).
- **Mô hình định giá:** AWS On-Demand Pricing (Không sử dụng Reserved Instance hay Savings Plans).
- **Đặc thù hệ thống:** Hệ thống chỉ phục vụ demo và chấm đồ án nên lưu lượng truy cập rất thấp.

### Bảng dự toán chi phí

| STT | AWS Service | Configuration | Quantity | Estimated Monthly Cost (USD) | Notes | Total (USD) |
|:---:|:---|:---|:---:|---:|:---|---:|
| 1 | Amazon VPC | Public Subnet (02), Private Application Subnet (02), Private Database Subnet (02), Internet Gateway (01), Security Group | 1 | 0.00 | Dịch vụ miễn phí | 0.00 |
| 2 | NAT Gateway | us-east-1 (0.045 USD/giờ) | 2 | 32.85 | 02 NAT Gateway | 65.70 |
| 3 | Amazon EC2 | t3.micro Linux (0.0104 USD/giờ) | 3 | 7.59 | 01 Backend, 02 EC2 trong ASG | 22.77 |
| 4 | Amazon EBS | gp3, 30 GB/EC2 (0.08 USD/GB-tháng) | 3 | 2.40 | Cấp phát cùng EC2 | 7.20 |
| 5 | Auto Scaling Group | Kèm theo Launch Template, AMI | 1 | 0.00 | Dịch vụ miễn phí | 0.00 |
| 6 | Application Load Balancer | Kèm theo Target Group (01) | 1 | 16.43 | Phí LCU không đáng kể | 16.43 |
| 7 | Amazon RDS | db.t3.micro, Single-AZ (0.017 USD/giờ) | 1 | 12.41 | Lưu trữ CSDL quan hệ | 12.41 |
| 8 | Amazon RDS Storage | 20 GB gp3 (0.115 USD/GB-tháng) | 1 | 2.30 | Dung lượng ổ cứng RDS | 2.30 |
| 9 | Amazon S3 | Standard, 5 GB (0.023 USD/GB-tháng) | 1 | 0.12 | Lưu trữ dữ liệu tĩnh | 0.12 |
| 10 | Amazon SQS | Standard Queue & DLQ | 2 | 0.00 | Miễn phí dưới 1 triệu request | 0.00 |
| 11 | AWS Secrets Manager | 01 Secret | 1 | 0.40 | 0.40 USD/secret/tháng | 0.40 |
| 12 | Amazon Cognito | Dưới 50.000 MAU | 1 | 0.00 | Dịch vụ miễn phí | 0.00 |
| 13 | AWS Systems Manager | Session Manager | 1 | 0.00 | Dịch vụ miễn phí | 0.00 |
| 14 | Amazon CloudWatch | Metrics + Logs cơ bản | 1 | 0.00 | Dịch vụ miễn phí | 0.00 |
| **Tổng** | | | | | | **127.33** |

### Phân tích và Đánh giá

**Tổng chi phí triển khai mỗi tháng:**
Tổng chi phí ước tính để duy trì hệ thống hoạt động 24/7 là **127.33 USD/tháng**.

**Phân tích thành phần chi phí:**
Khoản chi phí cao nhất thuộc về **NAT Gateway (65.70 USD, chiếm 51.6%)**, do kiến trúc sử dụng 02 NAT Gateway phân bổ để đáp ứng mạng Private. Đứng thứ hai là nhóm **Compute và Load Balancing (EC2 và ALB)** chiếm khoảng 30.7% tổng chi phí. Chi phí Database (RDS) chiếm khoảng 11.5%. Các dịch vụ về Storage, Messaging, Security và Monitoring chiếm tỉ trọng rất nhỏ hoặc hoàn toàn miễn phí.

**Đánh giá tính khả thi (AWS Credits 200 USD):**
Với giới hạn AWS Credits là **200 USD**, chi phí duy trì 127.33 USD/tháng là hoàn toàn phù hợp và an toàn. Hệ thống có thể duy trì hoạt động liên tục trong suốt khoảng 1.5 tháng để phục vụ quá trình demo và chấm đồ án mà không vượt quá ngân sách tín dụng cho phép.

**Đề xuất tối ưu hóa chi phí:**
Để tối ưu hóa chi phí mà không thay đổi kiến trúc hiện tại, có thể áp dụng các biện pháp sau:
- **Tắt các dịch vụ Compute ngoài giờ sử dụng:** Thiết lập AWS Lambda và EventBridge để tự động tắt (Stop) các instance EC2 và RDS vào ban đêm hoặc những khoảng thời gian không dùng đến, qua đó tiết kiệm đáng kể chi phí tính toán.
- **Giảm số lượng NAT Gateway:** Mặc dù theo kiến trúc chuẩn cần 02 NAT Gateway để dự phòng, nhưng đối với môi trường demo đồ án, có thể cấu hình Private Subnet trỏ tất cả về 01 NAT Gateway duy nhất. Việc này sẽ giảm ngay 50% chi phí mạng (tiết kiệm ~32.85 USD/tháng) mà vẫn duy trì đủ chức năng.

## 4. Cost and resource cleanup

- [AWS Pricing Calculator](https://calculator.aws/)
- [AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/)
- [AWS Billing and Cost Management](https://docs.aws.amazon.com/cost-management/latest/userguide/what-is-costmanagement.html)
