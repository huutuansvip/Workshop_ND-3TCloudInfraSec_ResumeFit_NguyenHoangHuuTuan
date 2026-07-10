---
title: "Setup NAT Gateway for Private Subnets"
date: 2026-07-09
weight: 3
chapter: false
pre: " <b> 5.3.3. </b> "
---

Allows instances in Private Subnets to connect to the internet one-way (to download packages, update software) but denies inbound connections originating from the internet.

1. Initialize two static **Elastic IPs**: `ResumeMatching-EIP` and `ResumeMatching-EIP-B`.

![Create Elastic IP](/images/5-Workshop/Tao_Elastic_IP.jpg)
<p align="center"><i>Create Elastic IP</i></p>

![Create Elastic IP B](/images/5-Workshop/Tao_Elastic_IP_B.jpg)
<p align="center"><i>Create Elastic IP B</i></p>

2. Create a **NAT Gateway** named `ResumeMatching-NAT` located at `Public-Subnet-A` and attach the first Elastic IP.

![Create NAT](/images/5-Workshop/Tao_NAT.jpg)
<p align="center"><i>Create NAT</i></p>

3. Create another **NAT Gateway** named `ResumeMatching-NAT-B` located at the remaining Availability Zone and attach the second Elastic IP to ensure High Availability.

![Create NAT B](/images/5-Workshop/Tao_NAT_B.jpg)
<p align="center"><i>Create NAT B</i></p>

4. Open the configuration of the Private App Route Tables, add route `0.0.0.0/0`, and point the `Target` to the respective NAT Gateways just initialized.

![Add Route Tables for Private App RT](/images/5-Workshop/Add_Route_Tables_cho_Private-App-RT.jpg)
<p align="center"><i>Add Route Tables for Private App RT</i></p>
