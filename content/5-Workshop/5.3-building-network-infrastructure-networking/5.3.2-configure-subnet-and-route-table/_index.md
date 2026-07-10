---
title: "Configure Subnet and Route Table"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.3.2. </b> "
---

Divide the VPC network range into subnets to isolate application tiers (Public for Load Balancer, Private App for EC2, Private DB for RDS).

1. Go to the **Subnets** section and sequentially create subnets with appropriate CIDR ranges:
* Public Subnets: `Public-Subnet-A` (`10.0.1.0/24`), `Public-Subnet-B` (`10.0.2.0/24`).
* Private App Subnets: `Private-App-A` (`10.0.11.0/24`), `Private-App-B` (`10.0.12.0/24`).
* Private DB Subnets: `Private-DB-A` (`10.0.21.0/24`), `Private-DB-B` (`10.0.22.0/24`).

![Create Public and Private subnets](/images/5-Workshop/Tao_cac_Public_va_Private_subnet.jpg)
<p align="center"><i>Create Public and Private subnets</i></p>

2. Create a public Route Table named `Public-RT` and attach it to the VPC.

![Create Public Route Table](/images/5-Workshop/Tao_Public_Route_Table.jpg)
<p align="center"><i>Create Public Route Table</i></p>

3. In the **Edit routes** section of `Public-RT`, add a route with `Destination` as `0.0.0.0/0` and point the `Target` to the Internet Gateway (`igw-...`).

![Add Routes](/images/5-Workshop/Add_Routes.jpg)
<p align="center"><i>Add Routes</i></p>

4. Associate `Public-RT` to 2 subnets: `Public-Subnet-A` and `Public-Subnet-B`.

![Associate Public Route Table](/images/5-Workshop/Gan_Public_Route_Table.jpg)
<p align="center"><i>Associate Public Route Table</i></p>

5. Create additional private Route Tables: `Private-App-RT`, `ResumeMatching-Private-App-RT-B`, and `Private-DB-RT`, then associate them respectively with the corresponding App Subnets and DB Subnets to ensure these tiers are not exposed to the internet.

![Create and associate Private App Route Table](/images/5-Workshop/Tao_va_gan_Private_App_Route_Table.jpg)
<p align="center"><i>Create and associate Private App Route Table</i></p>

![Create Route Table B](/images/5-Workshop/Tao_Route_Table_B.jpg)
<p align="center"><i>Create Route Table B</i></p>

![Create and associate Database Route Table](/images/5-Workshop/Tao_va_gan_Database_Route_Table.jpg)
<p align="center"><i>Create and associate Database Route Table</i></p>
