---
title: "Bản đề xuất"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 2. </b> "
---


# AI Resume Matching & Interview Preparation Platform
## Nền tảng Web đánh giá độ phù hợp CV và JD trên hạ tầng AWS chuẩn kiến trúc 3-Tier

### 1. Tóm tắt điều hành
Dự án phát triển nền tảng AI Resume Matching & Interview Preparation nhằm giải quyết bài toán tuyển dụng tự động. Hệ thống cho phép đánh giá độ phù hợp giữa CV và Job Description (JD) một cách nhanh chóng và chính xác. Được xây dựng trên kiến trúc AWS 3-Tier (3 lớp) có khả năng tự động co giãn, tối ưu chi phí. Cụm EC2 (Backend + Worker) chịu trách nhiệm phân tích CV và JD bằng cách gọi API OpenAI qua Internet.

### 2. Tuyên bố vấn đề
*Vấn đề hiện tại*
Việc đánh giá thủ công lượng lớn CV so với JD tốn rất nhiều thời gian của chuyên viên nhân sự (HR). Hơn nữa, việc sử dụng trực tiếp các dịch vụ AI (như OpenAI) để phân tích văn bản thô chưa qua xử lý thường dẫn đến lượng token tiêu thụ khổng lồ, gây chi phí vận hành đắt đỏ.

*Giải pháp*
Ứng dụng Web đánh giá độ phù hợp CV và JD dựa trên hạ tầng AWS chuẩn kiến trúc 3-Tier. Cụm EC2 (Backend + Worker) chịu trách nhiệm phân tích CV và JD bằng cách gọi API OpenAI qua Internet để tối ưu lượng token tiêu thụ và tiết kiệm chi phí.

*Lợi ích và hoàn vốn đầu tư (ROI)*
Hệ thống tự động hóa quá trình sàng lọc ứng viên, giúp HR tiết kiệm hàng chục giờ làm việc mỗi tuần. Thời gian hoàn vốn ngắn nhờ chi phí vận hành được tối ưu hoá thông qua kiến trúc Auto Scaling và High Availability.

### 3. Kiến trúc giải pháp
Kiến trúc được triển khai theo chuẩn 3-Tier trên AWS, đảm bảo tính sẵn sàng cao (High Availability), bảo mật và tự động hóa.

![AI Resume Matching Architecture](/images/2-Proposal/architecture.png)

*Dịch vụ AWS sử dụng*
- **Lớp Biên & Toàn Cầu (Global):** Mạng phân phối nội dung (CloudFront), tường lửa WAF và dịch vụ xác thực đang trong trạng thái dự kiến (Planned but not deployed - AWS account verification required), không phải là các dịch vụ đang hoạt động thực tế. Sử dụng Amazon S3 (Amazon Simple Storage Service) cho lưu trữ chung. Người dùng (Users) tương tác qua Internet Gateway (1) hoặc "tải lên qua Pre-signed URL" trực tiếp đến một S3 storage riêng (S3 CV/JD Storage) (5).
- **Mạng & Cân Bằng Tải (Inbound):** VPC 10.0.0.0/16 làm nền tảng. Internet Gateway (IGW) làm cửa ngõ duy nhất kết nối với Internet cho cả lưu lượng Inbound và Outbound (thông qua NAT Gateway). Application Load Balancer (ALB) nằm giữa các Vùng Sẵn Sàng (Availability Zones), nhận lưu lượng từ IGW và phân phối đến cụm Auto Scaling Group.
- **Tầng Ứng Dụng (Application):** Cụm EC2 (Backend + Worker) được đặt trong các Private App Subnets kín (Private App Subnet A & Private App Subnet B), xuyên qua 2 Vùng Sẵn Sàng (AZ A & AZ B) và được quản lý bởi một Auto Scaling Group (ASG) để tự co giãn theo tải. Giao tiếp nội bộ: EC2 (AZ A) kết nối với dịch vụ S3 storage và SQS (6), sau đó là Dead Letter Queue (DLQ). Luồng API OpenAI (AZ B) được thực hiện bằng cách EC2 (AZ B) đi ra ngoài qua NAT Gateway của Public Subnet B để gọi Internet Gateway.
- **Mạng Outbound & Nội Bộ:** Có **hai NAT Gateway**, một trong Public Subnet A và một trong Public Subnet B, đảm bảo khả năng dự phòng cao (High Availability) cho lưu lượng Outbound từ các Private Subnets. Giao tiếp đến SQS và S3 được hiển thị qua mạng, không thấy VPC Endpoints.
- **Tầng Cơ Sở Dữ Liệu (Database):** Dùng Amazon RDS PostgreSQL với cấu hình Multi-AZ. Có hai Private DB Subnets (Private DB Subnet A & Private DB Subnet B) được bảo vệ bởi một Security Group. RDS Primary (Master) ở AZ A. RDS Standby Replica ở AZ B với dữ liệu được đồng bộ liên tục (đường đứt nét). Luồng kết nối: EC2 ở AZ A kết nối trực tiếp đến RDS Primary (7). EC2 ở AZ B kết nối đến RDS Standby Replica thông qua một RDS Endpoints (đường đứt nét).
- **Quản Lý & Giám Sát:** Một cụm "Quản Lý & Bảo Mật" (Regional Vùng Bảo mật & Quản lý) bao gồm AWS Systems Manager, Amazon CloudWatch (logs) và AWS Secrets Manager (API Key).
- **Triển Khai (Deployment):** Nguồn mã đặt tại GitHub (Manual Deployment) được chỉ định là triển khai thủ công. Không sử dụng AWS CodeBuild hay AWS CodePipeline tự động trong kiến trúc hiện tại.

### 4. Triển khai kỹ thuật
*Các giai đoạn triển khai*
1. *Nghiên cứu & Thiết kế kiến trúc*: Phân tích yêu cầu, vẽ sơ đồ AWS và lên kịch bản gọi AI.
2. *Xây dựng hạ tầng cơ sở*: Triển khai VPC, Subnet, Route Table, IGW, NAT Gateways, RDS.
3. *Phát triển Ứng dụng & Tích hợp AI*: Viết code Backend/Worker trên EC2, thiết lập gọi API OpenAI.
4. *Triển khai & Frontend*: Triển khai thủ công từ GitHub, đưa Frontend lên S3.

*Yêu cầu kỹ thuật*
Kiến thức vững về AWS Networking (VPC, Subnetting), quản trị Database Multi-AZ. Kỹ năng lập trình Backend (Python/Node.js) cho việc tích hợp OpenAI.

### 5. Lộ trình & Mốc triển khai
- *Giai đoạn 1 (Tuần 1-2):* Lên thiết kế kiến trúc, cấu hình VPC mạng lưới và bảo mật.
- *Giai đoạn 2 (Tuần 3-5):* Xây dựng tầng CSDL (RDS) và tầng Ứng dụng (ASG, EC2), tích hợp AI.
- *Giai đoạn 3 (Tuần 6-7):* Phát triển Frontend, thiết lập S3 lưu trữ.
- *Giai đoạn 4 (Tuần 8):* Triển khai thủ công, kiểm thử chịu tải và hoàn thiện tài liệu.

### 6. Ước tính ngân sách
*Chi phí hạ tầng (Ước lượng hàng tháng)*
- **Amazon EC2 & ASG:** Tùy thuộc vào lượng tải, chi phí cơ bản cho 2 EC2 (dòng t3: t3.micro/t3.small).
- **Amazon RDS (Multi-AZ):** Chi phí cao nhất do chạy 2 node đồng thời (Primary & Standby).
- **NAT Gateway & Truyền Dữ Liệu:** Tính phí theo giờ và dung lượng dữ liệu xử lý.
- **WAF, CloudFront & S3:** Phí dựa trên lượng truy cập (Request) và lưu trữ tĩnh.
- **OpenAI API:** Tối ưu hóa nhờ service tiền xử lý.

### 7. Đánh giá rủi ro
*Ma trận rủi ro*
- Lỗi kết nối API OpenAI: Ảnh hưởng cao, xác suất thấp.
- Quá tải hệ thống khi có lượng lớn CV: Ảnh hưởng trung bình, xác suất thấp (đã có ASG).
- Chi phí vượt dự kiến: Ảnh hưởng trung bình, xác suất trung bình.

*Chiến lược giảm thiểu*
- Cấu hình Auto Scaling Group (ASG) co giãn linh hoạt theo lưu lượng CPU/Memory.
- Thiết lập CloudWatch Billing Alarm để cảnh báo ngay khi chi phí vượt mức.
- Sử dụng hàng đợi (Amazon SQS) để xử lý bất đồng bộ các luồng đánh giá CV nặng.

### 8. Kết quả kỳ vọng
*Cải tiến kỹ thuật*: Một hệ thống 3-Tier chuẩn an toàn, có tính sẵn sàng cao, với khả năng Failover của CSDL và tự động co giãn.
*Giá trị dài hạn*: Trở thành công cụ đắc lực cho các bộ phận HR, rút ngắn thời gian tuyển dụng và tối ưu hóa quy trình.