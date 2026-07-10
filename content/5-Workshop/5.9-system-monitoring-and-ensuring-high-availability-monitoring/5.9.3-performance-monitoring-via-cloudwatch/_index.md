---
title: "Performance Monitoring via CloudWatch"
date: 2026-07-09
weight: 3
chapter: false
pre: " <b> 5.9.3. </b> "
---

1. Access **CloudWatch**, select the **Metrics** menu to monitor parameters deeply.
2. **For EC2**: Filter EC2 Namespace, select `CPUUtilization`. Observe the chart to see processing spikes (e.g., `81.9%`) when AI runs heavy tasks, thereby setting automatic scaling Thresholds for ASG.

![CloudWatch is monitoring EC2](/images/5-Workshop/CloudWatch_dang_monitor_EC2.jpg)
<p align="center"><i>CloudWatch is monitoring EC2</i></p>

![EC2 Metrics](/images/5-Workshop/EC2_Metrics.jpg)
<p align="center"><i>EC2 Metrics</i></p>

3. **For ALB**: Filter metric `RequestCount` and `TargetResponseTime`. The correlation between surging Requests and changes in response time (e.g., `660.4 ms`) helps assess the smoothness of the user experience.

![CloudWatch monitor Load Balancer](/images/5-Workshop/CloudWatch_monitor_Load_Balancer.jpg)
<p align="center"><i>CloudWatch monitor Load Balancer</i></p>

![ALB Metrics](/images/5-Workshop/ALB_Metrics.jpg)
<p align="center"><i>ALB Metrics</i></p>
