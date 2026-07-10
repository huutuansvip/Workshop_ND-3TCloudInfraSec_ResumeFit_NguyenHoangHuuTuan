---
title: "Initialize S3 Bucket"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.5.1. </b> "
---

1. Switch to the **S3** service, click **Create bucket** to create a storage location for CVs and candidate documents.
![Create S3](/images/5-Workshop/Tao_S3.jpg)
<p align="center"><i>Create S3</i></p>
![Create Folder S3](/images/5-Workshop/Create_Folder_S3.jpg)
<p align="center"><i>Create Folder S3</i></p>

2. Name the bucket in the format `resume-matching-storage-[AWS-ACCOUNT-ID]-us-east-1`.

3. At the **Permissions** tab, proceed to edit **Cross-origin resource sharing (CORS)**. Add JSON content to configure `AllowedMethods` including: `GET`, `PUT`, `POST` to allow the web application to upload files to the bucket.
![Add CORS S3](/images/5-Workshop/Bo_sung_CORS_S3.jpg)
<p align="center"><i>Add CORS S3</i></p>
