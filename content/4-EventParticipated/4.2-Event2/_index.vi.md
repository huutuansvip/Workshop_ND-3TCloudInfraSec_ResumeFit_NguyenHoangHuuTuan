---
title: "Event 2"
date: 2026-05-23
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Bài thu hoạch “FCAJ Community Day”
*(Sự kiện gặp gỡ của cộng đồng FCAJ / AWS Study Group)*

### Mục Đích Của Sự Kiện
* **Mục tiêu của chương trình:** Không chỉ là nơi để nghe hội thảo, sự kiện còn là không gian để kết nối, truyền cảm hứng, khuyến khích mọi người chủ động bắt chuyện để tìm kiếm những người bạn hoặc đối tác mới.
* **Nội dung chính muốn truyền tải:** Đi qua 6 phiên chia sẻ xoay quanh từ AI, Cloud đến các câu chuyện thực tế. Trọng tâm nói về việc ứng phó với sự thay đổi của thị trường lao động thời AI, kiến trúc AWS (CloudFront, Amazon Q), cách viết Prompt hiệu quả với ngữ cảnh, tính xác suất của LLM, trải nghiệm thi Hackathon và thiết kế hệ thống Multi-Agent chuẩn doanh nghiệp (Enterprise).
* **Giá trị dành cho người tham dự:** Cung cấp góc nhìn thực tế và thiết thực từ những chuyên gia trực tiếp làm dự án; hiểu được cách thiết kế và vận hành một hệ thống an toàn, đáng tin cậy phục vụ đúng nhu cầu người dùng.
* **Đơn vị tổ chức:** Cộng đồng FCAJ (AWS Study Group).
* **Địa điểm tổ chức:** Tầng 26, tòa nhà Bitexco, số 02 đường Hải Triều, phường Sài Gòn, thành phố Hồ Chí Minh.
* **Vai trò trong sự kiện:** Người tham dự.

### Danh Sách Diễn Giả
* **Quỳnh Mai:** MC chương trình.
* **Nguyễn Gia Hưng:** Head of Solution Architect tại AWS Việt Nam, Người sáng lập FCAJ.
* **Speaker 1 - Anh Tịnh:** Platform Engineer tại Gotam X.
* **Speaker 2 - Chị Hải Anh:** Đang làm việc ở Pacific Việt Nam (Từng present ở AWS Singapore Summit, Silicon Valley).
* **Speaker 3 - Anh Thịnh:** DevOps Engineer.
* **Speaker 4 - Nhóm UTM:** Developers (Đồng nghiệp tại công ty chia sẻ về dự án thi Hackathon).
* **Speaker 5 - Anh Đức:** Chia sẻ về kỹ thuật và tối ưu hóa của mô hình ngôn ngữ lớn (LLM Optimization).
* **Speaker 6 - Chị Vy:** Đang công tác tại VBBank (VPBank), chia sẻ về hệ thống Enterprise Multi-agent.

### Nội Dung Nổi Bật

#### 1. Tổng quan vấn đề
* Ngành IT đang hoang mang vì AI phát triển nhanh chóng.
* Các kỹ sư thường dùng AI với những câu Prompt thiếu ngữ cảnh, gây ra hiện tượng "ảo giác" (hallucination).
* Khó khăn trong việc quản lý chi phí phát sinh bất thường từ Cloud (bill spike).
* Mô hình ngôn ngữ lớn (LLM) luôn trả về kết quả khác nhau dù cố định nhiệt độ bằng 0 (temperature = 0).
* Bài toán thiếu dữ liệu báo cáo tài chính khi chấm điểm tín dụng cho doanh nghiệp Startup.

#### 2. Giải pháp được giới thiệu
* Xây dựng sản phẩm (product) thực tế để ghi điểm thay vì chỉ làm bài tập demo.
* Cung cấp bối cảnh (context) đặc thù của doanh nghiệp cho AI thay vì các câu lệnh chung chung.
* Sử dụng cơ chế giá Flat-rate pricing của CloudFront để tối ưu chi phí hạ tầng và chống DDoS hiệu quả.
* Sử dụng hệ thống đa tác vụ (Multi-agent) để chia nhỏ chuyên môn thay vì bắt một mô hình AI duy nhất làm mọi việc.

#### 3. Công nghệ / Dịch vụ / Công cụ
* **AWS Services:** Amazon Q (QuickSight), Amazon CloudFront (OAC, Shield, WAF).
* **AI & Tools:** CrewAI, Bedrock Agent Core, LLM parameters (Temperature, Logits, Soft max, Arg max), Model Context Protocol (MCP).
* **Infrastructure as Code:** Terraform.

#### 4. Demo hoặc Case Study
* Demo Amazon Q import file Excel báo cáo kinh doanh để sinh ra dashboard phân tích thông tin.
* Case study thi Los Hackathon với ứng dụng *"UTM Morpo"* - tự động sinh giao diện UI từ hình ảnh phác thảo, hỗ trợ kéo thả và chỉnh sửa code trực tiếp.
* Demo host 2 model LLM (một trên AWS Bedrock, một chạy Local) với temperature = 0 để so sánh tính nhất quán của kết quả trả về.
* Case study xây dựng hệ thống tín dụng đánh giá Startup bằng Multi-agent tại ngân hàng.
* **Điểm đáng chú ý:** Căn bệnh "Internet Builder" - thói quen thấy tool, rule hay code nào trên mạng cũng kéo về dùng mà không hiểu rõ nó có hợp với dự án của công ty hay không. Sự bảo mật cực kỳ gắt gao trong các ngân hàng (Security sẽ tịch thu máy nếu tự ý cài cắm MCP lung tung).

### Những Gì Học Được

#### 1. Tư duy và phương pháp
* AI không thay thế con người, nhưng nó tạo ra một luồng công việc mới cho những người đi sửa lỗi (fix) và bảo trì (maintain) các sản phẩm do AI sinh ra.
* Khi thiết kế hệ thống, luôn phải trả lời được các câu hỏi: Ai xài, xài cái gì, tại sao xài và khi nào xài.

#### 2. Kiến thức kỹ thuật
* Hiểu rõ khái niệm Platform Engineer (tạo ra nền tảng IDP để Dev tự cấp phát tài nguyên hạ tầng).
* Nắm bắt cơ chế tối ưu chi phí hạ tầng (inference optimization) của các nhà cung cấp LLM, giải thích lý do tại sao kết quả trả về không bao giờ giống nhau hoàn toàn.

#### 3. Best practices
* Để có kết quả AI tốt, thay vì nhồi nhét, hãy tạo quy trình truyền tải tri thức (Knowledge transfer) bằng cách chắt lọc tài liệu nghiệp vụ từ các chuyên gia.
* Thường xuyên xoay vòng khóa bảo mật (Rotate API Key / IAM Access Key) để tránh rủi ro mất mát ngân sách lớn.
* Thiết lập một con Agent chuyên trách để kiểm tra và đối chiếu kết quả (output filtering/challenge) của các AI khác.

#### 4. Kinh nghiệm thực tế
* Việc copy/paste code từ AI mà không hiểu quy chuẩn công ty (coding standard) sẽ gây ra những bug nghiêm trọng trên Production.
* Trong doanh nghiệp, khi ai đó ra quyết định dựa trên kết quả của AI, người đó phải chịu hoàn toàn trách nhiệm pháp lý nếu xảy ra sai sót, không thể đổ lỗi cho AI.

### Ứng Dụng Vào Công Việc
* **Áp dụng cho dự án hiện tại:** Cấu hình lại các câu lệnh Prompt (context) sát với domain và quy trình của team. Điều chỉnh parameter (Temperature = 0.1 thay vì 0) để tránh lỗi LLM lặp lại từ vựng.
* **Công nghệ muốn thử nghiệm:** Áp dụng Terraform để viết Code quản lý hạ tầng (Infrastructure as Code) thay vì click tay, giúp việc rollback và scale dễ dàng hơn. Thử nghiệm Amazon Q để làm trợ lý summarize cuộc họp và tự gửi qua Teams/Email.
* **Ý tưởng cải thiện quy trình làm việc:** Xây dựng hệ thống Multi-Agent chia nhiệm vụ (Ví dụ: một con Research, một con Đánh giá rủi ro, một con Review). Cần lập bản đánh giá ROI (Return on Investment) để báo cáo sếp trước khi triển khai bất kỳ dự án AI nào.

### Trải Nghiệm Trong Event
* **Học hỏi từ diễn giả:** Nhận được các lời khuyên rất "thực chiến" từ những kỹ sư đang làm hệ thống lớn, giúp hiểu sâu sắc khoảng cách giữa "làm đồ án" và "làm cho doanh nghiệp".
* **Trải nghiệm thực hành:** Được xem các demo trực quan về cách tạo Dashboard bằng giọng nói hay cách gen ra web layout từ wireframe và có thể chỉnh sửa ngay lập tức.
* **Giao lưu và kết nối:** Các diễn giả thân thiện, khích lệ sự tự tin, tạo cơ hội cho mọi người giơ tay trả lời để tích lũy điểm cộng vào CV hoặc nhận credit của AWS.
* **Điều ấn tượng nhất:** Những chia sẻ gai góc về việc người tuyển dụng sẽ xem xét "sản phẩm thực tế" thay vì điểm số, và thực trạng copy code từ ChatGPT gây thảm họa tại VBBank.

### Bài Học Rút Ra
* **Kiến thức quan trọng nhất:** Nền tảng Kỹ thuật phần mềm (Software Engineering) mới là yếu tố cốt lõi giúp đưa một mô hình AI lên production chạy an toàn và có thể scale được. Bằng cấp và các kỹ năng cũ vẫn rất quan trọng để vượt qua vòng sàng lọc hồ sơ.
* **Kinh nghiệm thực tế:** "Ship in thì ship out" / "Garbage in, Garbage out" - Dữ liệu đưa vào là rác thì AI trả ra kết quả cũng là rác. Khi có quá nhiều ý tưởng (overthinking), cách tốt nhất là cắt bớt và tập trung hoàn thành một luồng tính năng cốt lõi duy nhất để đảm bảo giao hàng đúng hạn.
* **Định hướng học tập/phát triển tiếp theo:** Nâng cao tư duy AI (AI mindset / AI adoption) để áp dụng vào doanh nghiệp. Cần làm chủ một nhà cung cấp Cloud (như AWS) đi kèm kiến thức về bảo mật (Security, IAM) và Terraform thay vì chỉ tập trung học trí tuệ nhân tạo bề nổi. Bất kể hệ thống nào cũng phải nhớ 3 chữ: "an toàn", "đáng tin cậy" và "phục vụ người dùng".

---

### Một số hình ảnh khi tham gia sự kiện

![Diễn giả chia sẻ về bối cảnh trong AI](/images/4-EventParticipated/4.2-Event2/event2_photo1.png)
*Diễn giả thuyết trình chủ đề "Context is Everything - Making AI Actually Work for You"*

![Nhóm UTM chia sẻ về hành trình thi Hackathon](/images/4-EventParticipated/4.2-Event2/event2_photo2.png)
*Nhóm tác giả chia sẻ dự án UTM Morpo từ ý tưởng ban đầu đến sản phẩm thực tế tại Los Hackathon*

![Các phiên thảo luận trong sự kiện](/images/4-EventParticipated/4.2-Event2/event2_photo3.png)
*Toàn cảnh phiên chia sẻ kỹ thuật và giải đáp thắc mắc của sinh viên*

![Ảnh chụp lưu niệm cuối sự kiện](/images/4-EventParticipated/4.2-Event2/event2_photo4.jpg)
*Hình ảnh kỷ niệm cùng cộng đồng FCAJ và các diễn giả tại sự kiện*
