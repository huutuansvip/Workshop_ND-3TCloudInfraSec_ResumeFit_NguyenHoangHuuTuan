---
title: "Kết nối và cài đặt phần mềm"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.7.2. </b> "
---

1. Truy cập EC2 từ xa an toàn bằng **Systems Manager Fleet Manager**. Chọn Managed node đang Running và nhấn **Start terminal session**.

![Connect EC2 backend bằng Systems Manager](/images/5-Workshop/Connect_EC2_backend_bang_Systems_Manager.jpg)
<p align="center"><i>Connect EC2 backend bằng Systems Manager</i></p>

2. Thực thi lệnh cài đặt **Git** để kéo mã nguồn:
```bash
sudo dnf install git
```

![Cài GIT](/images/5-Workshop/Cai_GIT.jpg)
<p align="center"><i>Cài GIT</i></p>

3. Tiến hành cài đặt và khởi động **Docker** để chạy ứng dụng dạng container:
```bash
sudo dnf install -y docker
sudo systemctl enable docker
sudo systemctl start docker
```

![Cài Docker](/images/5-Workshop/Cai_Docker.jpg)
<p align="center"><i>Cài Docker</i></p>

![Kiểm tra trạng thái Docker](/images/5-Workshop/Kiem_tra_trang_thai_Docker.jpg)
<p align="center"><i>Kiểm tra trạng thái Docker</i></p>

4. Điều hướng tới thư mục `/opt` và tải source code từ GitHub:
```bash
cd /opt
sudo git clone http://github.com/thuanthien-tran/resume-fit.git
sudo chown -R ssm-user /opt/resume-fit
```

![Clone source lên EC2](/images/5-Workshop/Clone_source_len_EC2.jpg)
<p align="center"><i>Clone source lên EC2</i></p>
