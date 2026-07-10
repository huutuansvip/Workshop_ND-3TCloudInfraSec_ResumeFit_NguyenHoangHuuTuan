---
title: "Setup Relational Database Management System (RDS)"
date: 2026-07-09
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

Candidate data, evaluation history, and account information need to be stored structured and absolutely securely. In this section, we will deploy the Amazon RDS relational database with the PostgreSQL engine. Placing the Database deep within the Private Subnet ensures data is completely isolated from the Internet. Furthermore, to avoid exposing database passwords in the source code, we will use AWS Secrets Manager to encrypt and centrally manage all sensitive information (like DB password, OpenAI API Key), making retrieval secure and facilitating password rotation when necessary.

### Detailed contents:

{{% children /%}}
