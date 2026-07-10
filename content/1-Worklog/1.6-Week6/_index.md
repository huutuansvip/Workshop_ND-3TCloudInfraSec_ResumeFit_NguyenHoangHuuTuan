---
title: "Week 6 Worklog"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---
### Week 6 Objectives:

* Learn High Availability architectures on AWS using Elastic Load Balancing and Auto Scaling.
* Set up an Application Load Balancer (ALB) to distribute web traffic.
* Configure an Auto Scaling Group (ASG) to dynamically manage EC2 fleet scale according to utilization.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | **High Availability Architecture Study:**<br>- Study AWS High Availability (HA) design patterns, horizontal vs. vertical scaling strategies, target group health status evaluations, and auto-scaling triggers. | 25/05/2026 | 25/05/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Custom Machine Image Creation:**<br>- Stop the active EC2 web server instance temporarily to ensure filesystem consistency.<br>- Create a custom Amazon Machine Image (AMI) from the EC2 instance containing the pre-configured Nginx environment and site assets. | 26/05/2026 | 26/05/2026 | [How to Create an AMI from EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami-ebs.html) |
| 4 | **Auto Scaling Policies Configuration:**<br>- Create an EC2 Launch Template using the custom AMI; define instance profile role, security group, and storage parameters.<br>- Build an Auto Scaling Group (ASG) using this Launch Template across multiple subnets, setting target limits (Min: 1 instance, Desired: 2 instances, Max: 4 instances). | 27/05/2026 | 27/05/2026 | [Amazon EC2 Auto Scaling Guide](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html) |
| 5 | **Application Load Balancer Provisioning:**<br>- Deploy an Application Load Balancer (ALB) in public subnets; configure security groups to accept HTTP traffic.<br>- Map ALB routing listeners to redirect incoming requests to the target group managed by the Auto Scaling Group. | 28/05/2026 | 29/05/2026 | [AWS Auto Scaling & Load Balancer Tutorial (YouTube)](https://www.youtube.com/watch?v=0mwgbiJae5Q) |
| 6 | **High Load Autoscaling Verification:**<br>- Install the `stress` utility on the active scaling instances; run commands to push instance CPU load above 80%.<br>- Monitor the ASG console to verify scale-out processes launching new instances, and check scale-in teardowns when CPU load settles. | 29/05/2026 | 29/05/2026 | [Testing Auto Scaling Policies](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scale-based-on-demand.html) |

### Week 6 Achievements:

* **High Availability Setup:** Designed and deployed a resilient, multi-subnet compute architecture capable of surviving server outages.
* **Server Image Templating:** Streamlined server duplication by creating custom AMIs and reusable Launch Templates.
* **Automated Web Workload Balancing:** Configured an Application Load Balancer to perform real-time health checks and distribute web traffic.
* **Dynamic Resource Scaling:** Built Auto Scaling policies that dynamically scale EC2 instances based on real-time CPU utilization.
* **Validated Under Load:** Confirmed correct autoscaling behaviors by simulating high CPU loads, demonstrating cloud agility.