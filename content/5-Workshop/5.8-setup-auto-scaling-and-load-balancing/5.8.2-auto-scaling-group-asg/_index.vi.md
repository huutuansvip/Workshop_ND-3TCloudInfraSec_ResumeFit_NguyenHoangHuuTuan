---
title: "Auto Scaling Group (ASG)"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.8.2. </b> "
---

1. Tạo Auto Scaling Group `ResumeMatching-ASG` và liên kết với Launch template `ResumeMatching-LT`.

![Tạo ASG](/images/5-Workshop/Tao_ASG.jpg)
<p align="center"><i>Tạo ASG</i></p>

2. Chỉnh sửa Desired capacity lên thành `2`. ASG sẽ tự động launch ra các EC2 instances mới ở trạng thái Initializing nhằm phục vụ dự phòng và mở rộng.

![ASG tạo thêm EC2](/images/5-Workshop/ASG_tao_them_EC2.jpg)
<p align="center"><i>ASG tạo thêm EC2</i></p>

![ASG tạo EC2 mới sau khi cập nhật AMI](/images/5-Workshop/ASG_tao_EC2_moi_sau_khi_cap_nhat_AMI.jpg)
<p align="center"><i>ASG tạo EC2 mới sau khi cập nhật AMI</i></p>
