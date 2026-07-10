---
title: "Deploy Compute and Server Configuration"
date: 2026-07-09
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

After the foundational infrastructure is complete, the next step is to launch compute servers to run the application source code. We will use the Amazon EC2 service to create Backend servers. This process includes securely connecting to the server via Systems Manager (without opening SSH port 22 to the internet), installing necessary environments like Git, Docker, and downloading the entire application source code from the repository. This is a crucial stepping stone to packaging the server into a standard image (AMI) for future auto-scaling.

### Detailed contents:

{{% children /%}}
