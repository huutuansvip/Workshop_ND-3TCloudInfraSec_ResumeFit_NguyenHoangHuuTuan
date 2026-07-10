---
title: "Resume Fit Application Testing"
date: 2026-07-09
weight: 10
chapter: false
pre: " <b> 5.10. </b> "
---

1. Test through the ALB's API endpoint (e.g., `[...elb.amazonaws.com/api/ready](https://...elb.amazonaws.com/api/ready)`) to receive JSON `{"status": "ready"}` proving the entire Backend and Database have been successfully linked.
![Test operation via ALB DNS](/images/5-Workshop/Test_hoat_dong_bang_DNS_cua_ALB.jpg)
<p align="center"><i>Test operation via ALB DNS</i></p>
![Proceed to check connections](/images/5-Workshop/Tien_hanh_kiem_tra_cac_ket_noi.jpg)
<p align="center"><i>Proceed to check connections</i></p>

2. Access the Frontend Domain/IP. At the **System Login** interface, proceed to create an account and log in to the workspace.
![Registration interface](/images/5-Workshop/giao_dien_dang_ky.jpg)
<p align="center"><i>Registration interface</i></p>
![Login interface](/images/5-Workshop/giao_dien_dang_nhap.jpg)
<p align="center"><i>Login interface</i></p>

3. Run the main workflow: Create a new Job Description (JD) and upload the candidate's CV.
![Create job interface](/images/5-Workshop/giao_dien_buoc_1_tao_ten_cong_viec_ung_tuyen.jpg)
<p align="center"><i>Create job interface</i></p>
![JD list interface](/images/5-Workshop/giao_dien_danh_sach_JD.jpg)
<p align="center"><i>JD list interface</i></p>
![Upload CV JD interface](/images/5-Workshop/giao_dien_buoc_2_upload_CV_JD.jpg)
<p align="center"><i>Upload CV JD interface</i></p>
![Upload CV JD interface (Part 2)](/images/5-Workshop/giao_dien_buoc_2_upload_CV_JD_Part-2.jpg)
<p align="center"><i>Upload CV JD interface (Part 2)</i></p>
![CV list interface](/images/5-Workshop/giao_dien_danh_sach_CV.jpg)
<p align="center"><i>CV list interface</i></p>

4. Request the system to analyze. AI will return a **Detailed Candidate Report** including:
![View results interface](/images/5-Workshop/giao_dien_buoc_3_xem_ket_qua_ung_vien.jpg)
<p align="center"><i>View results interface</i></p>

* Rank match and overall percentage fit (e.g., 60%).
![Fit level evaluation interface](/images/5-Workshop/giao_dien_danh_gia_muc_do_phu_hop.jpg)
<p align="center"><i>Fit level evaluation interface</i></p>
![Score analysis evaluation interface](/images/5-Workshop/giao_dien_danh_gia_phan_tich_diem_so.jpg)
<p align="center"><i>Score analysis evaluation interface</i></p>
* Analysis of missing professional skills (like Cybersecurity, C#, ELK).
![Skills evaluation interface](/images/5-Workshop/giao_dien_danh_gia_ky_nang.jpg)
<p align="center"><i>Skills evaluation interface</i></p>
* Interview recommendations and automated generation of technical interview questions based on the specific project context in the CV.
![Recommendations evaluation interface](/images/5-Workshop/giao_dien_danh_gia_khuyen_nghi.jpg)
<p align="center"><i>Recommendations evaluation interface</i></p>
![Interview questions evaluation interface](/images/5-Workshop/giao_dien_danh_gia_cau_hoi_phong_van.jpg)
<p align="center"><i>Interview questions evaluation interface</i></p>
*(Other information such as candidate analysis and extracted text)*
![Candidate analysis evaluation interface](/images/5-Workshop/giao_dien_danh_gia_phan_tich_ung_vien.jpg)
<p align="center"><i>Candidate analysis evaluation interface</i></p>
![Extracted text evaluation interface](/images/5-Workshop/giao_dien_danh_gia_van_ban_trich_xuat.jpg)
<p align="center"><i>Extracted text evaluation interface</i></p>
![CV JD evaluation history interface](/images/5-Workshop/giao_dien_lich_su_danh_gia_CV_JD.jpg)
<p align="center"><i>CV JD evaluation history interface</i></p>
![Suitable candidate ranking interface](/images/5-Workshop/giao_dien_xep_hang_ung_vien_phu_hop.jpg)
<p align="center"><i>Suitable candidate ranking interface</i></p>
![Debugger debugging information interface](/images/5-Workshop/giao_dien_thong_tin_go_loi_debugger.jpg)
<p align="center"><i>Debugger debugging information interface</i></p>
