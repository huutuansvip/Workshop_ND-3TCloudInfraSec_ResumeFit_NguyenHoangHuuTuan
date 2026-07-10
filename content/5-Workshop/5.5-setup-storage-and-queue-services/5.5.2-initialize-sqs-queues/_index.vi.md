---
title: "Khởi tạo SQS Queues"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.5.2. </b> "
---

Sử dụng hàng đợi để tách biệt luồng xử lý AI nặng nề ra khỏi luồng phản hồi web chính.

1. Chuyển đến giao diện **SQS**. Tạo một hàng đợi Standard có tên `ResumeMatching-DLQ` (Dead Letter Queue) dùng để hứng các message bị lỗi trong quá trình xử lý.
![Tạo queue](/images/5-Workshop/Tao_queue.jpg)
<p align="center"><i>Tạo queue</i></p>

2. Khởi tạo hàng đợi chính mang tên `ResumeMatching-Queue`.
![Tạo main queue](/images/5-Workshop/Tao_main_queue.jpg)
<p align="center"><i>Tạo main queue</i></p>

3. Bật tính năng **Dead-letter queue** trên hàng đợi chính, trỏ đến ARN của `ResumeMatching-DLQ` và thiết lập `Maximum receives` = `3`.
