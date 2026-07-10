---
title: "Giám sát hiệu suất qua CloudWatch"
date: 2026-07-09
weight: 3
chapter: false
pre: " <b> 5.9.3. </b> "
---

1. Truy cập **CloudWatch**, chọn menu **Metrics** để giám sát sâu các thông số.
2. **Đối với EC2**: Lọc Namespace EC2, chọn `CPUUtilization`. Quan sát biểu đồ để thấy các đỉnh gai xử lý (ví dụ `81.9%`) khi AI chạy tác vụ nặng, từ đó thiết lập Threshold mở rộng tự động cho ASG.

![CloudWatch đang monitor EC2](/images/5-Workshop/CloudWatch_dang_monitor_EC2.jpg)
<p align="center"><i>CloudWatch đang monitor EC2</i></p>

![EC2 Metrics](/images/5-Workshop/EC2_Metrics.jpg)
<p align="center"><i>EC2 Metrics</i></p>

3. **Đối với ALB**: Lọc metric `RequestCount` và `TargetResponseTime`. Sự tương quan giữa việc tăng vọt lượng Request và sự thay đổi của thời gian phản hồi (ví dụ `660.4 ms`) giúp đánh giá tính trơn tru của trải nghiệm người dùng.

![CloudWatch monitor Load Balancer](/images/5-Workshop/CloudWatch_monitor_Load_Balancer.jpg)
<p align="center"><i>CloudWatch monitor Load Balancer</i></p>

![ALB Metrics](/images/5-Workshop/ALB_Metrics.jpg)
<p align="center"><i>ALB Metrics</i></p>
