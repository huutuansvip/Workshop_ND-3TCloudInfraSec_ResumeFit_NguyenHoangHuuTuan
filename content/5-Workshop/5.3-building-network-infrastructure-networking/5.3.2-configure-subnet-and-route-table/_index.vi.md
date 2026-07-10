---
title: "Cấu hình Subnet và Route Table"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.3.2. </b> "
---

Chia nhỏ dải mạng VPC thành các mạng con để phân tách các tầng ứng dụng (Public cho Load Balancer, Private App cho EC2, Private DB cho RDS).

1. Truy cập mục **Subnets** và tạo lần lượt các subnet với các dải CIDR phù hợp:
* Public Subnets: `Public-Subnet-A` (`10.0.1.0/24`), `Public-Subnet-B` (`10.0.2.0/24`).
* Private App Subnets: `Private-App-A` (`10.0.11.0/24`), `Private-App-B` (`10.0.12.0/24`).
* Private DB Subnets: `Private-DB-A` (`10.0.21.0/24`), `Private-DB-B` (`10.0.22.0/24`).
![Tạo các Public và Private subnet](/images/5-Workshop/Tao_cac_Public_va_Private_subnet.jpg)
<p align="center"><i>Tạo các Public và Private subnet</i></p>

2. Tạo một Route Table công khai với tên `Public-RT` và gán vào VPC.
![Tạo Public Route Table](/images/5-Workshop/Tao_Public_Route_Table.jpg)
<p align="center"><i>Tạo Public Route Table</i></p>

3. Trong phần **Edit routes** của `Public-RT`, thêm route có `Destination` là `0.0.0.0/0` và trỏ `Target` đến Internet Gateway (`igw-...`).
![Add Routes](/images/5-Workshop/Add_Routes.jpg)
<p align="center"><i>Add Routes</i></p>

4. Gán (Associate) `Public-RT` vào 2 subnets: `Public-Subnet-A` và `Public-Subnet-B`.
![Gán Public Route Table](/images/5-Workshop/Gan_Public_Route_Table.jpg)
<p align="center"><i>Gán Public Route Table</i></p>

5. Tạo thêm các Route Table riêng tư là `Private-App-RT`, `ResumeMatching-Private-App-RT-B` và `Private-DB-RT`, sau đó lần lượt gán chúng cho các App Subnet và DB Subnet tương ứng để đảm bảo các tầng này không lộ ra internet.
![Tạo và gán Private App Route Table](/images/5-Workshop/Tao_va_gan_Private_App_Route_Table.jpg)
<p align="center"><i>Tạo và gán Private App Route Table</i></p>
![Tạo Route Table B](/images/5-Workshop/Tao_Route_Table_B.jpg)
<p align="center"><i>Tạo Route Table B</i></p>
![Tạo và gán Database Route Table](/images/5-Workshop/Tao_va_gan_Database_Route_Table.jpg)
<p align="center"><i>Tạo và gán Database Route Table</i></p>
