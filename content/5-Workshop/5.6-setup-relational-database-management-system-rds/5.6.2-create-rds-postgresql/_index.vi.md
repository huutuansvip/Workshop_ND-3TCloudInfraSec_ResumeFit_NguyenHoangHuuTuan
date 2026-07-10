---
title: "Tạo RDS PostgreSQL"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.6.2. </b> "
---

1. Truy cập giao diện **RDS**, chọn mục **Subnet groups** và tạo một subnet group tên `resumematching-dbsubnetgroup` trỏ vào VPC và gom 2 subnet `Private-DB-A`, `Private-DB-B` lại với nhau.
![Tạo DB Subnet Group](/images/5-Workshop/Tao_DB_Subnet_Group.jpg)
<p align="center"><i>Tạo DB Subnet Group</i></p>

2. Tiến hành khởi tạo Database (DB identifier: `resume-matching-db`) với Engine là **PostgreSQL** và instance class là `db.t3.micro`.
![Tạo RDS database](/images/5-Workshop/Tao_RDS_database.jpg)
<p align="center"><i>Tạo RDS database</i></p>

3. Sau khi tạo thành công, copy Endpoint của Database và dán cập nhật vào khóa `HOST` trong Secrets Manager.
