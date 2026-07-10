---
title: "Xây dựng Hạ tầng Mạng (Networking)"
date: 2026-07-09
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

Trong phần này, chúng ta sẽ tiến hành xây dựng nền tảng mạng (Networking) vững chắc và bảo mật trên AWS. Một kiến trúc mạng tốt là tiền đề để các dịch vụ khác hoạt động ổn định và an toàn. Chúng ta sẽ bắt đầu bằng việc khởi tạo Virtual Private Cloud (VPC) - không gian mạng cô lập dành riêng cho ứng dụng. Sau đó, hệ thống mạng sẽ được chia nhỏ thành các Subnet (mạng con) Public và Private nhằm phân tách rõ ràng giữa các tầng (Load Balancer, Web Server, Database). Cuối cùng, NAT Gateway sẽ được thiết lập để đảm bảo các máy chủ nằm trong mạng Private có thể truy cập Internet một chiều một cách an toàn để cập nhật phần mềm.

### Nội dung chi tiết:

{{% children /%}}
