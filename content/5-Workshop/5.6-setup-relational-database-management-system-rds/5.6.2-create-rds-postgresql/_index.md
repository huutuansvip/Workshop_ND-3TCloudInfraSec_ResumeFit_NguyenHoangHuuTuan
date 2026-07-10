---
title: "Create RDS PostgreSQL"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.6.2. </b> "
---

1. Access the **RDS** interface, select the **Subnet groups** section and create a subnet group named `resumematching-dbsubnetgroup` pointing to the VPC and grouping the 2 subnets `Private-DB-A`, `Private-DB-B` together.

![Create DB Subnet Group](/images/5-Workshop/Tao_DB_Subnet_Group.jpg)
<p align="center"><i>Create DB Subnet Group</i></p>

2. Proceed to initialize the Database (DB identifier: `resume-matching-db`) with Engine as **PostgreSQL** and instance class as `db.t3.micro`.

![Create RDS database](/images/5-Workshop/Tao_RDS_database.jpg)
<p align="center"><i>Create RDS database</i></p>

3. After successful creation, copy the Database Endpoint and paste it to update the `HOST` key in Secrets Manager.
