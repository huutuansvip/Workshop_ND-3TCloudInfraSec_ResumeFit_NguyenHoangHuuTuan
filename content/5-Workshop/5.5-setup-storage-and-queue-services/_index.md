---
title: "Setup Storage and Queue Services"
date: 2026-07-09
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

To handle large volumes of input data and complex AI tasks without bottlenecking the web system, we need to decouple the data flow. This section demonstrates how to use Amazon S3 to create a secure, infinitely scalable storage repository for candidates' CVs and documents. Next, we will set up Amazon SQS - a message queuing service - as an intermediary bridge between the web server (Backend) and the background processing server (Worker). This architecture allows the web application to respond quickly to users while heavy tasks are queued and processed sequentially, ensuring the system is not overloaded.

### Detailed contents:

{{% children /%}}
