---
title: "Blog 3"
date: 2026-06-29
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---
# A POWERFUL FEATURE OF AWS LAKE FORMATION: UNIFYING DATA ACCESS

*Posted by: Vo Tran Bao Toan*

Recently, while exploring Data Lake architectures on AWS, I came across an interesting article from AWS about Lake Formation and wanted to share it with everyone.

Looking at the architecture, we can see:
* **EMR Spark** reads/writes data directly from/to S3 using IAM Permissions.
* **Lake Formation** manages table-level permissions inside the AWS Glue Data Catalog.
* **Athena** queries data based on Lake Formation permissions.

This leads to a common dilemma in real-world environments: you can query data through Athena without issues, but when using Spark to read S3 files directly, you hit an `Access Denied` error.

This happens because Athena and Spark use two different authorization mechanisms:
* Athena → Authorized via **AWS Lake Formation**
* Spark direct S3 reads → Authorized via **IAM / S3 Bucket Policies**

AWS recently introduced a new feature to address this challenge. **AWS Lake Formation** can now grant temporary credentials for Spark to access S3 data directly based on permissions defined within Lake Formation. This is achieved via the API:

`GetTemporaryDataLocationCredentials()`

### IN MY OPINION, THE KEY ADVANTAGES OF THIS FEATURE ARE:

* **Centralized Administration:** Reduces the overhead of configuring data permission policies in multiple places.
* **Configuration Consistency:** Prevents `Access Denied` errors caused by configuration mismatches between data access layers.
* **Streamlined Workloads:** Significantly simplifies data paths for Spark jobs, ETL pipelines, and Machine Learning workflows.
* **Enhanced Auditing:** Allows security teams to easily audit and track direct data access activities via AWS CloudTrail logs.

### PREREQUISITES & CURRENT LIMITATIONS:

* The S3 Location must be registered with AWS Lake Formation.
* Requires Amazon EMR versions 6.15.0+ or 7.1.0+.
* Apache Iceberg table format is not yet supported.
* Cross-Region data access is not yet supported.

Overall, I see this as a highly useful enhancement for AWS Data Lakes, especially in environments utilizing both Athena and EMR Spark to process big data workloads.

---

### ARCHITECTURE DIAGRAM

![Lake Formation Architecture Diagram](/images/blog3_architecture.png)

---

### REFERENCES & LINKS

* **Group Post Link:** [AWS Study Group - AWS Lake Formation Post](https://www.facebook.com/groups/awsstudygroupfcj/posts/2191055074992786/)
* **AWS Big Data Blog:** [Access Amazon S3 data files directly using AWS Lake Formation permissions](https://aws.amazon.com/blogs/big-data/access-amazon-s3-data-files-directly-using-aws-lake-formation-permissions/)