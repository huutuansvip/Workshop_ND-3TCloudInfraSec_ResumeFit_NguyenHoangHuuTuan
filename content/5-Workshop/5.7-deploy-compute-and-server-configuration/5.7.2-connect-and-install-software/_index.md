---
title: "Connect and install software"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.7.2. </b> "
---

1. Securely access EC2 remotely using **Systems Manager Fleet Manager**. Select the Running Managed node and click **Start terminal session**.
![Connect EC2 backend using Systems Manager](/images/5-Workshop/Connect_EC2_backend_bang_Systems_Manager.jpg)
<p align="center"><i>Connect EC2 backend using Systems Manager</i></p>

2. Execute the command to install **Git** to pull the source code:
```bash
sudo dnf install git
```
![Install GIT](/images/5-Workshop/Cai_GIT.jpg)
<p align="center"><i>Install GIT</i></p>

3. Proceed to install and start **Docker** to run the application as a container:
```bash
sudo dnf install -y docker
sudo systemctl enable docker
sudo systemctl start docker
```
![Install Docker](/images/5-Workshop/Cai_Docker.jpg)
<p align="center"><i>Install Docker</i></p>
![Check Docker status](/images/5-Workshop/Kiem_tra_trang_thai_Docker.jpg)
<p align="center"><i>Check Docker status</i></p>

4. Navigate to the `/opt` directory and download the source code from GitHub:
```bash
cd /opt
sudo git clone http://github.com/thuanthien-tran/resume-fit.git
sudo chown -R ssm-user /opt/resume-fit
```
![Clone source to EC2](/images/5-Workshop/Clone_source_len_EC2.jpg)
<p align="center"><i>Clone source to EC2</i></p>
