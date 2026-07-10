---
title: "Week 3 Worklog"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---
### Week 3 Objectives:

* Learn Amazon Virtual Private Cloud (VPC) core networking concepts.
* Design and implement a secure VPC topology containing public and private subnets.
* Route traffic between subnets and secure EC2 instance communication.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | **Virtual Networking Study:**<br>- Learn virtual network fundamentals: IP addressing, CIDR notation (classless inter-domain routing), subnet calculation rules, Route Tables, and Internet Gateways (IGW).<br>- Study private IP vs public IP spaces and VPC routing mechanisms. | 04/05/2026 | 04/05/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Custom VPC Setup:**<br>- Design and build a custom Amazon VPC with CIDR block `10.0.0.0/16`.<br>- Create a Public Subnet (`10.0.1.0/24`) and a Private Subnet (`10.0.2.0/24`) inside a single Availability Zone (AZ) to segregate systems. | 05/05/2026 | 05/05/2026 | [AWS VPC Tutorial (YouTube)](https://www.youtube.com/watch?v=N6qtN0c_e9A) |
| 4 | **Internet Routing Setup:**<br>- Create and attach an Internet Gateway (IGW) to the custom VPC to enable public outbound connectivity.<br>- Design a custom Public Route Table, add a route for `0.0.0.0/0` targeting the IGW, and associate this Route Table with the Public Subnet. | 06/05/2026 | 06/05/2026 | [Amazon VPC Route Tables Guide](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html) |
| 5 | **Subnet VM Deployment & Security:**<br>- Launch a Public EC2 instance (representing a web server) and a Private EC2 instance (representing a database server).<br>- Configure Security Groups for both instances; build inbound rules for the Private EC2 to allow traffic exclusively from the Public EC2 security group. | 07/05/2026 | 08/05/2026 | [AWS Security Groups Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html) |
| 6 | **Connectivity Verification & Troubleshooting:**<br>- SSH into the Public EC2 instance, and from there, run ping/SSH commands to connect to the Private EC2 instance using its local IP (`10.0.2.x`).<br>- Verify that the Private EC2 instance cannot be reached directly from the public internet. | 08/05/2026 | 08/05/2026 | [AWS VPC Troubleshooting Guide](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-troubleshooting.html) |

### Week 3 Achievements:

* **Custom VPC Network Deployment:** Designed and built a custom VPC network from scratch, defining IP allocation boundaries.
* **Segregated Network Subnets:** Implemented multi-tier network topologies separating internet-facing compute nodes from private databases.
* **Configured Custom Routing Tables:** Successfully established public routing paths via Internet Gateways and custom route tables.
* **Implemented Stateful Firewalls:** Utilured Security Groups to enforce strict network access controls, ensuring instances only accept traffic from authorized nodes.
* **Validated Multi-Tier Connectivity:** Verified internal connectivity using jump-host setups while maintaining private subnet isolation from external networks.