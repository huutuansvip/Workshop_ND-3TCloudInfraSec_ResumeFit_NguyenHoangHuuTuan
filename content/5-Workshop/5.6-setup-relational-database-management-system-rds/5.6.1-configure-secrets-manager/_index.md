---
title: "Configure Secrets Manager"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 5.6.1. </b> "
---

1. Access **AWS Secrets Manager**, create a secret named `ResumeMatching-Secrets` to store sensitive information.
![Create Secret](/images/5-Workshop/Tao_Secret.jpg)
<p align="center"><i>Create Secret</i></p>

2. Configure the **Secret value** section with Key/value fields such as `HOST`, `PORT` (`5432`), `USERNAME`, `PASSWORD`, and `OPENAI_API_KEY` of the application.
![Update Secrets manager](/images/5-Workshop/Cap_nhat_Secrets_manager.jpg)
<p align="center"><i>Update Secrets manager</i></p>
