---
title: "Auto Scaling Group (ASG)"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.8.2. </b> "
---

1. Create Auto Scaling Group `ResumeMatching-ASG` and link it with the Launch template `ResumeMatching-LT`.

![Create ASG](/images/5-Workshop/Tao_ASG.jpg)
<p align="center"><i>Create ASG</i></p>

2. Edit Desired capacity to `2`. ASG will automatically launch new EC2 instances in Initializing state to serve for redundancy and scaling.

![ASG creates additional EC2](/images/5-Workshop/ASG_tao_them_EC2.jpg)
<p align="center"><i>ASG creates additional EC2</i></p>

![ASG creates new EC2 after AMI update](/images/5-Workshop/ASG_tao_EC2_moi_sau_khi_cap_nhat_AMI.jpg)
<p align="center"><i>ASG creates new EC2 after AMI update</i></p>
