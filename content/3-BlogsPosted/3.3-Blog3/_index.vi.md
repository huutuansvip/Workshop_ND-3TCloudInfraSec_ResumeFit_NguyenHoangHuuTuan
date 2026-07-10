---
title: "Blog 3"
date: 2026-06-29
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---
# MỘT TÍNH NĂNG KHÁ SỰ HỮU ÍCH CỦA AWS LAKE FORMATION

*Đăng bởi: Võ Trần Bảo Toàn*

Gần đây khi tìm hiểu về Data Lake trên AWS, mình đọc được một bài viết khá thú vị từ AWS về Lake Formation nên muốn chia sẻ lại với mọi người.

Nhìn vào mô hình hệ thống ban đầu, ta có thể thấy:
* **EMR Spark** đọc/ghi dữ liệu trực tiếp với S3 thông qua IAM Permissions.
* **Lake Formation** quản lý quyền trên các bảng dữ liệu trong Glue Catalog.
* **Athena** truy vấn dữ liệu dựa trên quyền của Lake Formation.

Điều này dẫn đến một tình huống khá phổ biến trong thực tế: bạn có thể truy vấn (query) dữ liệu bằng Athena rất bình thường, nhưng khi dùng Spark để đọc trực tiếp file trong S3 lại gặp ngay lỗi `Access Denied`.

Nguyên nhân là vì Athena và Spark đang sử dụng hai cơ chế phân quyền khác nhau:
* Athena → Được ủy quyền qua **Lake Formation**
* Spark đọc trực tiếp file S3 → Được ủy quyền qua **IAM / S3 Policy**

AWS vừa giới thiệu một tính năng mới giúp giải quyết triệt để vấn đề này. **Lake Formation** giờ đây có thể cấp thông tin đăng nhập tạm thời (temporary credentials) để EMR Spark truy cập trực tiếp dữ liệu trong S3 dựa trên chính quyền hạn đã được cấu hình trong Lake Formation thông qua API:

`GetTemporaryDataLocationCredentials()`

### THEO MÌNH, ĐIỂM HAY NHẤT CỦA TÍNH NĂNG NÀY LÀ:

* **Tập trung hóa quản trị:** Giảm việc phải cấu hình phân quyền ở nhiều nơi khác nhau.
* **Đồng bộ hóa cấu hình:** Hạn chế tối đa lỗi `Access Denied` do lệch cấu hình giữa các dịch vụ.
* **Tối ưu hóa quy trình:** Thuận tiện hơn rất nhiều cho các workload xử lý dữ liệu Spark, các luồng ETL và mô hình Machine Learning.
* **Kiểm toán an toàn dữ liệu:** Dễ dàng theo dõi và giám sát mọi hoạt động truy cập dữ liệu trực tiếp thông qua nhật ký của AWS CloudTrail.

### MỘT VÀI LƯU Ý KHI TRIỂN KHAI TÍNH NĂNG NÀY:

* Vị trí lưu trữ S3 (S3 Location) bắt buộc phải được đăng ký (registered) với Lake Formation.
* Yêu cầu phiên bản Amazon EMR 6.15.0+ hoặc 7.1.0+.
* Chưa hỗ trợ định dạng bảng Apache Iceberg.
* Chưa hỗ trợ truy xuất đa vùng (Cross-Region).

Mình thấy đây là một cải tiến khá hữu ích cho các hệ thống Data Lake trên AWS, đặc biệt trong các môi trường doanh nghiệp sử dụng kết hợp cả Athena và EMR Spark để xử lý dữ liệu lớn.

---

### SƠ ĐỒ KIẾN TRÚC HỆ THỐNG

![Lake Formation Architecture Diagram](/images/blog3_architecture.png)

---

### LIÊN KẾT THAM KHẢO

* **Link bài đăng Group:** [AWS Study Group - AWS Lake Formation Post](https://www.facebook.com/groups/awsstudygroupfcj/posts/2191055074992786/)
* **Tài liệu hướng dẫn AWS:** [Access Amazon S3 data files directly using AWS Lake Formation permissions](https://aws.amazon.com/vi/blogs/big-data/access-amazon-s3-data-files-directly-using-aws-lake-formation-permissions/)