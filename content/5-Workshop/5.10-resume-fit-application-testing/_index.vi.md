---
title: "Kiểm thử Ứng dụng Resume Fit"
date: 2026-07-09
weight: 10
chapter: false
pre: " <b> 5.10. </b> "
---

1. Kiểm thử thông qua endpoint API của ALB (e.g., `[...elb.amazonaws.com/api/ready](https://...elb.amazonaws.com/api/ready)`) để nhận về JSON `{"status": "ready"}` chứng minh toàn bộ Backend và Database đã được liên kết thành công.
![Test hoạt động bằng DNS của ALB](/images/5-Workshop/Test_hoat_dong_bang_DNS_cua_ALB.jpg)
<p align="center"><i>Test hoạt động bằng DNS của ALB</i></p>
![Tiến hành kiểm tra các kết nối](/images/5-Workshop/Tien_hanh_kiem_tra_cac_ket_noi.jpg)
<p align="center"><i>Tiến hành kiểm tra các kết nối</i></p>

2. Truy cập Domain/IP của Frontend. Tại giao diện **Đăng nhập hệ thống**, tiến hành tạo tài khoản và đăng nhập vào không gian làm việc.
![Giao diện đăng ký](/images/5-Workshop/giao_dien_dang_ky.jpg)
<p align="center"><i>Giao diện đăng ký</i></p>
![Giao diện đăng nhập](/images/5-Workshop/giao_dien_dang_nhap.jpg)
<p align="center"><i>Giao diện đăng nhập</i></p>

3. Chạy luồng công việc chính: Tạo mô tả công việc (JD) mới và tải lên CV của ứng viên.
![Giao diện tạo công việc](/images/5-Workshop/giao_dien_buoc_1_tao_ten_cong_viec_ung_tuyen.jpg)
<p align="center"><i>Giao diện tạo công việc</i></p>
![Giao diện danh sách JD](/images/5-Workshop/giao_dien_danh_sach_JD.jpg)
<p align="center"><i>Giao diện danh sách JD</i></p>
![Giao diện upload CV JD](/images/5-Workshop/giao_dien_buoc_2_upload_CV_JD.jpg)
<p align="center"><i>Giao diện upload CV JD</i></p>
![Giao diện upload CV JD (Phần 2)](/images/5-Workshop/giao_dien_buoc_2_upload_CV_JD_Part-2.jpg)
<p align="center"><i>Giao diện upload CV JD (Phần 2)</i></p>
![Giao diện danh sách CV](/images/5-Workshop/giao_dien_danh_sach_CV.jpg)
<p align="center"><i>Giao diện danh sách CV</i></p>

4. Yêu cầu hệ thống phân tích. AI sẽ trả về **Báo cáo chi tiết ứng viên** bao gồm:
![Giao diện xem kết quả](/images/5-Workshop/giao_dien_buoc_3_xem_ket_qua_ung_vien.jpg)
<p align="center"><i>Giao diện xem kết quả</i></p>

* Độ khớp cấp bậc và tổng quan phần trăm phù hợp (VD: 60%).
![Giao diện đánh giá mức độ phù hợp](/images/5-Workshop/giao_dien_danh_gia_muc_do_phu_hop.jpg)
<p align="center"><i>Giao diện đánh giá mức độ phù hợp</i></p>
![Giao diện đánh giá phân tích điểm số](/images/5-Workshop/giao_dien_danh_gia_phan_tich_diem_so.jpg)
<p align="center"><i>Giao diện đánh giá phân tích điểm số</i></p>
* Phân tích các kỹ năng chuyên môn còn thiếu (như Cybersecurity, C#, ELK).
![Giao diện đánh giá kỹ năng](/images/5-Workshop/giao_dien_danh_gia_ky_nang.jpg)
<p align="center"><i>Giao diện đánh giá kỹ năng</i></p>
* Khuyến nghị phỏng vấn và sinh tự động các câu hỏi phỏng vấn kỹ thuật dựa trên chính ngữ cảnh dự án trong CV.
![Giao diện đánh giá khuyến nghị](/images/5-Workshop/giao_dien_danh_gia_khuyen_nghi.jpg)
<p align="center"><i>Giao diện đánh giá khuyến nghị</i></p>
![Giao diện đánh giá câu hỏi phỏng vấn](/images/5-Workshop/giao_dien_danh_gia_cau_hoi_phong_van.jpg)
<p align="center"><i>Giao diện đánh giá câu hỏi phỏng vấn</i></p>
*(Các thông tin khác như phân tích ứng viên và trích xuất văn bản)*
![Giao diện đánh giá phân tích ứng viên](/images/5-Workshop/giao_dien_danh_gia_phan_tich_ung_vien.jpg)
<p align="center"><i>Giao diện đánh giá phân tích ứng viên</i></p>
![Giao diện đánh giá văn bản trích xuất](/images/5-Workshop/giao_dien_danh_gia_van_ban_trich_xuat.jpg)
<p align="center"><i>Giao diện đánh giá văn bản trích xuất</i></p>
![Giao diện lịch sử đánh giá CV JD](/images/5-Workshop/giao_dien_lich_su_danh_gia_CV_JD.jpg)
<p align="center"><i>Giao diện lịch sử đánh giá CV JD</i></p>
![Giao diện xếp hạng ứng viên phù hợp](/images/5-Workshop/giao_dien_xep_hang_ung_vien_phu_hop.jpg)
<p align="center"><i>Giao diện xếp hạng ứng viên phù hợp</i></p>
![Giao diện thông tin gỡ lỗi debugger](/images/5-Workshop/giao_dien_thong_tin_go_loi_debugger.jpg)
<p align="center"><i>Giao diện thông tin gỡ lỗi debugger</i></p>
