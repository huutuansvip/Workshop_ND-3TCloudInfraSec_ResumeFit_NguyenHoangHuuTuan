---
title: "Week 4 Worklog"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---
### Week 4 Objectives:

* Learn Amazon Elastic Compute Cloud (EC2) instances lifecycle, families, and AMIs.
* Deploy a functional Nginx web server on Linux EC2.
* Configure security rules and persistent IP address mapping (Elastic IP).

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | **EC2 Platform Study:**<br>- Study EC2 virtualization families (T family for burstable, M family for general purpose), instance sizing standards, storage structures (instance stores vs. EBS volumes), and Key Pair security concepts. | 11/05/2026 | 11/05/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Provisioning Virtual Machines:**<br>- Provision a `t2.micro` EC2 instance utilizing Ubuntu Linux AMI within the custom VPC Public Subnet.<br>- Allocate 20GB gp3 EBS storage volume and download the private key (.pem file) securely to local workstation. | 12/05/2026 | 12/05/2026 | [Host your personal site on AWS EC2 Instance (YouTube)](https://www.youtube.com/watch?v=Islmm-LMu38) |
| 4 | **Web Server Configuration:**<br>- Perform secure terminal connection using SSH key authentication to the EC2 public endpoint.<br>- Update system repository packages (`sudo apt update`) and install Nginx web server package. Verify Nginx daemon runs. | 13/05/2026 | 13/05/2026 | [Nginx Installation and Setup Guide](https://nginx.org/en/docs/beginners_guide.html) |
| 5 | **Security Configuration & Publishing:**<br>- Customize default Nginx web root folder, writing dynamic HTML landing page detailing personal internship details.<br>- Configure Security Group inbound rules, allowing public access to HTTP port 80 and HTTPS port 443 while restricting SSH port 22 access. | 14/05/2026 | 15/05/2026 | [AWS Security Groups for EC2 Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/working-with-security-groups.html) |
| 6 | **IP Address Preservation Configuration:**<br>- Request an Elastic IP from AWS, associate it to the web server, and test website load.<br>- Reboot the EC2 instance and verify the assigned public IP remains static. | 15/05/2026 | 15/05/2026 | [Elastic IP Addresses Reference](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) |

### Week 4 Achievements:

* **Compute Deployment Competency:** Mastered virtual machine resource provisioning, disk volume allocation, and OS image selection on AWS EC2.
* **Functional Web Server Host:** Deployed Nginx web server engine, hosting custom HTML files.
* **Custom Security Isolation:** Configured network firewalls to allow public web services access while securing management interfaces.
* **Persistent Networking Anchors:** Resolved IP cycling hazards across instance restarts using Elastic IP associations.
* **Secure Remote Terminal Mastery:** Gained hands-on skills in remote system administration via secure SSH keys.