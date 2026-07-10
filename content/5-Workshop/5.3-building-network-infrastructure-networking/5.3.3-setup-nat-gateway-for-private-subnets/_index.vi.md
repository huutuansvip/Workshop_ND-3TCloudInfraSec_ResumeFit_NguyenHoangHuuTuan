---
title: "Thiết lập NAT Gateway cho Private Subnets"
date: 2026-07-09
weight: 3
chapter: false
pre: " <b> 5.3.3. </b> "
---

Giúp các instance ở Private Subnet kết nối ra internet một chiều (để tải package, cập nhật phần mềm) nhưng từ chối các kết nối khởi tạo từ internet đi vào.

1. Khởi tạo hai **Elastic IP** tĩnh là `ResumeMatching-EIP` và `ResumeMatching-EIP-B`.

![Tạo Elastic IP](/images/5-Workshop/Tao_Elastic_IP.jpg)
<p align="center"><i>Tạo Elastic IP</i></p>

![Tạo Elastic IP B](/images/5-Workshop/Tao_Elastic_IP_B.jpg)
<p align="center"><i>Tạo Elastic IP B</i></p>

2. Tạo **NAT Gateway** tên `ResumeMatching-NAT` đặt tại `Public-Subnet-A` và gắn Elastic IP thứ nhất.

![Tạo NAT](/images/5-Workshop/Tao_NAT.jpg)
<p align="center"><i>Tạo NAT</i></p>

3. Tạo thêm **NAT Gateway** tên `ResumeMatching-NAT-B` đặt tại Availability Zone còn lại và gắn Elastic IP thứ hai nhằm đảm bảo tính sẵn sàng cao (High Availability).

![Tạo NAT B](/images/5-Workshop/Tao_NAT_B.jpg)
<p align="center"><i>Tạo NAT B</i></p>

4. Mở cấu hình của các Route Table Private App, thêm route `0.0.0.0/0` và trỏ `Target` về các NAT Gateway tương ứng vừa khởi tạo.

![Add Route Tables cho Private App RT](/images/5-Workshop/Add_Route_Tables_cho_Private-App-RT.jpg)
<p align="center"><i>Add Route Tables cho Private App RT</i></p>
