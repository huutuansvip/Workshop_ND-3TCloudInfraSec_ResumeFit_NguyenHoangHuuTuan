---
title: "Check Auto Scaling Group operation"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.9.1. </b> "
---

1. Access the **EC2** service, navigate to the **Instances** menu.
2. Observe the system automatically initializing new EC2s named `ResumeMatching-ASG-Instance` evenly distributed across different Availability Zones.
3. Some old servers may display a `Terminated` status. This is proof that ASG is working correctly: automatically revoking old servers and launching new servers upon configuration changes or system errors.
