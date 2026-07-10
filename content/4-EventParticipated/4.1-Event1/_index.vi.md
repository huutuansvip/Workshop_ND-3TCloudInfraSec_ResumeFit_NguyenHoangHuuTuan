---
title: "Event 1"
date: 2026-05-09
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch “FCAJ Community Day”
*(Sự kiện gặp gỡ của cộng đồng FCAJ / AWS Study Group)*

### Mục Đích Của Sự Kiện
* **Mục tiêu của chương trình:** Tạo ra môi trường và cơ hội để các bạn trẻ mạnh dạn chia sẻ kiến thức, rèn luyện kỹ năng thuyết trình và phong thái tự tin trước đám đông.
* **Nội dung chính muốn truyền tải:** Sự kiện không chỉ chia sẻ về các khía cạnh kỹ thuật (technical) mà còn tập trung vào tư duy (mindset), bao gồm: cách "hack" não bộ để nghiện học, tối ưu hóa Prompt Engineering, định hướng nghề nghiệp và sự liêm chính trong kỷ nguyên AI, và phương pháp phát triển phần mềm kết hợp AI hiệu quả.
* **Giá trị dành cho người tham dự:** Người tham gia nhận được các phương pháp học tập hiệu quả để xây dựng các dự án lớn, biết cách áp dụng AI để tăng năng suất làm việc thay vì bị phụ thuộc, hiểu rõ tiêu chí đánh giá của nhà tuyển dụng, và tiếp cận các quy trình chuẩn trong phát triển phần mềm.
* **Đơn vị tổ chức:** Cộng đồng FCAJ / AWS Study Group.
* **Địa điểm tổ chức:** Tầng 26, tòa nhà Bitexco, số 02 đường Hải Triều, phường Sài Gòn, thành phố Hồ Chí Minh.
* **Vai trò trong sự kiện:** Người tham dự.

### Danh Sách Diễn Giả
Sự kiện có sự góp mặt của nhiều diễn giả với các chủ đề thiết thực:
* **Diễn giả 1 (Long - Ban tổ chức):** Trình bày về chủ đề *"Hack não bộ với Dopamine"*.
* **Diễn giả 2 (Thịnh):** Trình bày về *"Ultimate Prompt Engineering"* và kiến trúc AWS.
* **Diễn giả 3 (Khang):** Solution Architect tại *Cloud Kinetics*.
* **Diễn giả 4 (Thảo):** Software Developer tại *Ngân hàng Quốc tế Việt Nam (VIB)*.

### Nội Dung Nổi Bật

#### 1. Tổng quan vấn đề
* Sinh viên dễ chán học do việc học mang lại kết quả chậm, không tiết ra "dopamine" nhanh như khi lướt mạng xã hội hay chơi game.
* Sử dụng AI với các câu lệnh chung chung sẽ trả về kết quả kém chất lượng, tốn chi phí (token) và đôi khi sinh ra "ảo giác" (hallucination).
* Sinh viên IT hoang mang không biết AI có thay thế công việc của mình hay không.
* Việc giao phó cho AI viết code toàn bộ dự án từ đầu sẽ dẫn đến việc AI quên ngữ cảnh, tạo ra những đoạn code "rác" không thể sử dụng.

#### 2. Giải pháp được giới thiệu
* Đánh lừa não bộ bằng cách chia nhỏ việc học, áp dụng quy tắc 2 phút và dùng "nỗi sợ mất chuỗi" (streak) để duy trì động lực.
* Sử dụng cấu trúc Prompt 7 thành phần (Role, Task, Context, Format...) để tương tác hiệu quả với AI.
* Tập trung xây dựng kiến thức nền tảng (Foundation) thật vững chắc vì công nghệ sẽ thay đổi nhưng tư duy giải quyết vấn đề thì không.
* Áp dụng phương pháp BMX (BPM Method), chia nhỏ dự án thành các Document, Epic và Story trước khi cho AI tự động code từng phần.

#### 3. Công nghệ / Dịch vụ / Công cụ
* **Hệ sinh thái AWS:** CloudFront, S3, Cognito, API Gateway, Lambda (Serverless Backend), Bedrock, DynamoDB, CloudWatch.
* **AI Models:** Gemini, Claude.
* **Công cụ mới:** Extension tối ưu Prompt trên trình duyệt và công cụ mã nguồn mở BMX tích hợp trong IDE.

#### 4. Demo hoặc Case Study
* Trình diễn (Demo) kiến trúc dự án thực tế trên nền tảng AWS kết hợp Amazon Bedrock.
* Demo công cụ Prompt Optimizer để tự động cải thiện câu lệnh trực tiếp trên trình duyệt web.
* Giới thiệu quy trình lên ý tưởng và tạo tài liệu dự án bằng AI thông qua phương pháp BMX.
* **Điểm đáng chú ý:** AI không thay thế con người mà chỉ "khuếch đại" (amplify) năng lực của họ; nếu bạn kém, AI sẽ làm bạn lộ rõ cái kém, nếu bạn giỏi, AI sẽ giúp bạn làm việc nhanh gấp đôi.

### Những Gì Học Được

#### 1. Tư duy và phương pháp
* Tuyệt đối không được "outsource" (thuê ngoài) sự tư duy của chính mình cho AI; bạn có thể dùng AI để viết code nhưng bạn bắt buộc phải hiểu cốt lõi của giải pháp.

#### 2. Kiến thức kỹ thuật
* Hiểu về khái niệm Token trong AI, sự khác nhau giữa các phương pháp tư duy của AI như *Chain of Thought* và *Tree of Thought*.
* Biết cách xây dựng một kiến trúc Serverless căn bản trên AWS.

#### 3. Best practices
* Để làm việc với AI hiệu quả, cần chia một đầu vào (input) dài thành các phần nhỏ hơn.
* Trong quy trình phần mềm, hãy để AI đóng vai trò theo từng vị trí cụ thể (như PM, Architect, Dev, Tester) xử lý từng task riêng biệt nhằm tránh tình trạng nhầm lẫn ngữ cảnh (hallucination).

#### 4. Kinh nghiệm thực tế
* Khi đi phỏng vấn, nhà tuyển dụng không chỉ nhìn vào việc bạn làm đúng hay sai, mà họ quan tâm đến việc lý do tại sao (Why) bạn lại chọn giải pháp đó.

### Ứng Dụng Vào Công Việc
* **Áp dụng cho dự án hiện tại:** Có thể ngay lập tức chia nhỏ khối lượng kiến thức cần học/công việc cần làm thành các mốc nhỏ (ví dụ: học 10 phút, làm tính năng trong 2 phút) để không bị "ngợp".
* **Công nghệ muốn thử nghiệm:** Khám phá Amazon Bedrock để gọi các LLM khác nhau, hoặc tải công cụ BMX mã nguồn mở trên GitHub để áp dụng vào IDE.
* **Ý tưởng cải thiện quy trình làm việc:** Áp dụng phương pháp tài liệu hóa (document-driven) cho AI; thay vì bắt AI code ngay, hãy yêu cầu nó viết tài liệu (PRD, Architect, Story) thật chuẩn chỉnh rồi mới sinh code dựa trên các tài liệu đó.

### Trải Nghiệm Trong Event
* **Học hỏi từ diễn giả:** Tiếp thu được những góc nhìn rất thực tế từ những người đang làm vị trí tuyển dụng và quản lý dự án (Solution Architect, Software Developer).
* **Trải nghiệm thực hành:** Được quan sát cách các dịch vụ AWS liên kết với nhau qua kiến trúc cụ thể và cách các AI extension hoạt động trên trình duyệt.
* **Giao lưu và kết nối:** Diễn giả khuyến khích các sinh viên nên làm việc nhóm, không nên đi một mình để học cách quản lý, giao tiếp và mở rộng mạng lưới quan hệ (network). Sự kiện cũng có phần hỏi đáp thực tế với sinh viên.
* **Điều ấn tượng nhất:** Quan điểm về "Sự liêm chính" (Integrity) trong công việc. Việc xử lý triệt để các trường hợp ngoại lệ (corner cases) hay dọn dẹp tài nguyên sau khi dùng xong dù không ai kiểm tra chính là tố chất quyết định một người có tiến xa được hay không.

### Bài Học Rút Ra
* **Kiến thức quan trọng nhất:** Việc sở hữu tư duy nền tảng (Foundation) vững chắc quan trọng hơn việc chạy theo việc học thuộc các công cụ, framework hay dịch vụ bề nổi.
* **Kinh nghiệm thực tế:** Một công việc mang lại giá trị không chỉ nằm ở mức lương (Salary), mà còn nằm ở Kinh nghiệm (Experience), Mạng lưới quan hệ (Network), Kiến thức (Knowledge) và Tố chất (Attitude/Skills). Chấp nhận mắc sai lầm để học hỏi là đặc quyền khi còn trẻ.
* **Định hướng học tập/phát triển tiếp theo:** Luôn đặt câu hỏi "Tại sao" (Why) tối thiểu 5 lần cho mọi quyết định của mình trong công việc cũng như trong định hướng cuộc đời. Thay vì tiêu tốn thời gian lướt mạng xã hội, hãy xây dựng thói quen tìm tòi kiến thức mới và mạnh dạn đứng lên chia sẻ nó.

---

### Một số hình ảnh khi tham gia sự kiện

![Hình ảnh diễn giả chia sẻ về BMX](/images/4-EventParticipated/4.1-Event1/event1_photo1.png)
*Diễn giả giới thiệu phương pháp phát triển phần mềm kết hợp AI bằng công cụ BMX*

![Hình ảnh về Prompt Engineering](/images/4-EventParticipated/4.1-Event1/event1_photo2.png)
*Chủ đề thảo luận về tầm quan trọng của Prompt Engineering và cách giao tiếp hiệu quả với AI*

![Hình ảnh diễn giả chia sẻ về Growth Mindset](/images/4-EventParticipated/4.1-Event1/event1_photo3.png)
*Thảo luận về tư duy phát triển (Growth Mindset) và việc luôn đặt câu hỏi "Tại sao"*

![Hình ảnh lưu niệm cùng cộng đồng FCAJ](/images/4-EventParticipated/4.1-Event1/event1_photo4.png)
*Hình ảnh lưu niệm cuối chương trình cùng các thành viên và ban tổ chức cộng đồng FCAJ*
