---
title: "Week 5 Worklog"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---
### Week 5 Objectives:

* Deploy cloud storage and relational database systems on AWS.
* Configure Amazon S3 for static site hosting and media asset storage.
* Launch a secure Amazon RDS database instance and establish connection from the EC2 web server.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | **Cloud Storage & Relational Database study:**<br>- Study cloud storage tiers (S3 Standard, S3 Intelligent-Tiering, S3 Glacier), bucket permissions, policy properties, and IAM integration.<br>- Study Amazon RDS engine configurations, storage autoscaling, and private network isolation models. | 18/05/2026 | 18/05/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **S3 Static Website Hosting:**<br>- Create an S3 Bucket with unique naming; upload HTML, CSS, and asset files.<br>- Configure S3 Bucket Policy to allow public read access (`GetObject` permissions) and enable Static Website Hosting feature. | 19/05/2026 | 19/05/2026 | [Hosting a Static Website on Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html) |
| 4 | **RDS Database Isolation Provisioning:**<br>- Launch an Amazon RDS instance running MySQL engine (free tier config); configure Subnet Groups to isolate RDS resources in VPC Private Subnets.<br>- Set secure master username and store database credentials safely. | 20/05/2026 | 21/05/2026 | [How to connect EC2 to private RDS instance (YouTube)](https://www.youtube.com/watch?v=TRkp54ekyY4) |
| 5 | **Database Firewall Security Setup:**<br>- Create a database Security Group; configure inbound traffic rules to permit access on MySQL port 3306 exclusively from the EC2 web server security group ID. | 21/05/2026 | 22/05/2026 | [AWS RDS Security Group Rules](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_SettingUpAPIs.html#CHAP_SettingUpAPIs.SecurityGroups) |
| 6 | **Connectivity Testing & Database Interaction:**<br>- SSH into the EC2 web server; install MySQL Client CLI software (`sudo apt install mysql-client`).<br>- Connect to the RDS instance endpoint, create test schemas, insert logs, and verify write operations. | 22/05/2026 | 22/05/2026 | [Connecting to an Amazon RDS Database Instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html) |

### Week 5 Achievements:

* **Serverless Front-end Deployment:** Hosted static assets and site front-ends directly on S3 buckets, reducing execution fees.
* **Isolated Cloud Database Setup:** Provisioned a relational database (RDS MySQL) completely isolated from direct public internet routing.
* **VPC Data Path Segregation:** Configured granular security group constraints linking application servers to databases securely.
* **Hands-on Database Operations:** Mastered connecting, querying, and verifying relational databases using database client tools on servers.