---
title: "Event 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---
# Bài thu hoạch Automated Prompt Engineering: Enhancing LLM Output Quality

### Mục Đích Của Sự Kiện

* Chia sẻ nghệ thuật giao tiếp với AI (The Art of Communicating with AI) và cách nâng cao chất lượng đầu ra của các Mô hình Ngôn ngữ Lớn (LLM).
* Chỉ ra tầm quan trọng của việc đặt câu lệnh (Prompt Engineering) và những ảnh hưởng tiêu cực của việc đặt câu lệnh sai cách.
* Cung cấp các cấu trúc, nguyên tắc và kỹ thuật từ cơ bản đến nâng cao để tương tác hiệu quả với LLM.
* Giới thiệu giải pháp "Proptimizer" - tự động hóa việc tối ưu prompt cùng với kiến trúc hệ thống chạy trên đám mây AWS.

## Danh Sách Diễn Giả

* **Nguyễn Tuấn Thịnh** - DevOps/Cloud Engineer, First Cloud AI Journey.

## Nội Dung Nổi Bật

Đưa ra các ảnh hưởng tiêu cực của việc đặt câu lệnh kém

* **Kết quả chung chung:** Sử dụng các câu lệnh chung chung (Generic prompts) sẽ chỉ nhận lại những đầu ra chung chung.
* **Tốn kém chi phí:** Việc lãng phí token do không tối ưu câu lệnh sẽ làm tăng chi phí sử dụng AI.
* **Thiếu tính nhất quán:** Các chỉ thị mơ hồ (Ambiguous instructions) khiến AI trả về các kết quả không đồng nhất.
* **Giảm năng suất:** Việc giao tiếp kém với AI làm mất thời gian và giảm hiệu suất công việc.

Chuyển đổi sang phương pháp đặt câu lệnh chuẩn (Great Prompt)

Một câu lệnh tuyệt vời cần phải bao gồm các thành phần cốt lõi sau:

* **Role:** Vai trò mà AI cần đóng vai (VD: Chuyên gia tư vấn nghề nghiệp).
* **Instruction:** Nhiệm vụ cụ thể AI cần làm.
* **Context:** Các thông tin nền tảng liên quan.
* **Input Data:** Dữ liệu, văn bản cần được xử lý.
* **Output Format:** Định dạng, cấu trúc, văn phong đầu ra.
* **Examples:** Đưa ra vài ví dụ mẫu (few-shot) để AI làm theo.
* **Constraints/Guidelines:** Các quy định về độ dài, những điều cần tập trung hoặc tránh.

Kinh tế học Token (Token Economics)

* **Bản chất Token:** LLM đọc và tạo văn bản dựa trên các "token" (các đơn vị nhỏ hơn từ, không phải lúc nào cũng là một từ hoàn chỉnh) và số lượng token sẽ khác biệt tùy thuộc vào ngôn ngữ sử dụng.
* **Sự chênh lệch chi phí:** Chi phí token đầu vào (Input) rẻ hơn so với token đầu ra (Output). (Ví dụ tham khảo: Token đầu vào giá \$5.00/1 triệu tokens, trong khi Token đầu ra là \$25.00/1 triệu tokens).

Các kỹ thuật Prompt nâng cao (Advanced Techniques)

* **Chain-of-Thought (CoT):** Hướng dẫn AI suy luận từng bước logic.
* **Self-Consistency:** Kết hợp cùng CoT để AI đưa ra nhiều luồng suy nghĩ và chọn ra đáp án phổ biến, hợp lý nhất.
* **Tree-of-Thoughts (ToT):** Suy luận dưới dạng cấu trúc cây để đánh giá nhiều hướng đi.
* Kỹ thuật **Retrieval-Augmented Generation (RAG)** và **Role Prompting**.

Kiến trúc hệ thống tối ưu hóa (Proptimizer Architecture)

Giải pháp Proptimizer là tiện ích mở rộng trình duyệt giúp tối ưu prompt, được xây dựng 100% Serverless trên AWS với chi phí hạ tầng bằng không (\$0, không bao gồm dịch vụ Bedrock):

* **Frontend & Giao thức:** Sử dụng AWS CloudFront (CDN) và Amazon S3 lưu trữ nội dung tĩnh.
* **Bảo mật & Backend:** Amazon Cognito quản lý xác thực người dùng; Amazon API Gateway điều hướng traffic và AWS Lambda xử lý logic backend mà không cần quản lý máy chủ.
* **Tích hợp AI & Dữ liệu:** Kết nối với nhiều mô hình AI (Claude, GPT) qua Amazon Bedrock mà không cần tự huấn luyện, đồng thời lưu trữ dữ liệu lịch sử prompt tốc độ siêu cao bằng Amazon DynamoDB.
* **Giám sát:** Quản lý log và hiệu năng bằng Amazon CloudWatch Logs & Metrics.

## Những Gì Học Được

Tư Duy Thiết Kế

* **Tư duy giao tiếp rõ ràng:** Cần mô tả cụ thể những việc **NÊN LÀM (DOs)** thay vì tập trung vào những việc KHÔNG NÊN (DON'Ts).
* **Tối ưu hệ thống:** Cần sử dụng các dấu phân cách (Delimiters) để chia nhỏ cấu trúc prompt và bẻ nhỏ các văn bản đầu vào (Break long inputs) để AI dễ tiêu hóa thông tin.
* Cho phép AI trả lời **"Tôi không biết"** để ngăn chặn việc bịa đặt thông tin (hallucination), không nên yêu cầu AI làm toán phức tạp.

Kiến Trúc Kỹ Thuật

* Nắm bắt được mô hình tích hợp công nghệ AWS và Generative AI.
* Hiểu được cơ chế sử dụng **Amazon Bedrock** như một cổng kết nối tới các LLMs nền tảng để gia tăng sức mạnh ứng dụng một cách dễ dàng.
* Cách thiết kế cơ sở dữ liệu **NoSQL DynamoDB** phù hợp cho các truy vấn với thời gian phản hồi tính bằng mili-giây.

Ứng Dụng Vào Công Việc

* **Áp dụng cấu trúc Prompt 7 thành phần** (Role, Instruction, Context, v.v.) vào các dự án hiện tại để đạt hiệu quả tương tác với LLM tốt nhất.
* **Tối ưu chi phí AI (Token Economics):** Viết câu lệnh tinh gọn, loại bỏ từ thừa để giảm chi phí token lãng phí cho các tác vụ hàng ngày.
* **Sử dụng Advanced Prompting:** Áp dụng kỹ thuật Chain-of-Thought (CoT) vào các bài toán cần suy luận logic hoặc phân tích mã nguồn.
* **Thiết kế ứng dụng nội bộ:** Lên ý tưởng (pilot) xây dựng các công cụ hỗ trợ công việc nội bộ tích hợp AI dựa trên kiến trúc Serverless (Lambda, Bedrock, S3) tham khảo từ Proptimizer.

## Trải nghiệm trong event

Học hỏi từ các diễn giả có chuyên môn cao

* Bài trình bày của chuyên gia Nguyễn Tuấn Thịnh mang lại một góc nhìn kết hợp độc đáo giữa trí tuệ nhân tạo (LLM) và hạ tầng điện toán đám mây (Cloud/DevOps), giúp tôi hiểu rõ không chỉ cách dùng AI mà còn cách xây dựng công cụ xoay quanh nó.

Trải nghiệm kỹ thuật thực tế

* Hình dung được rất rõ ràng cách luồng dữ liệu đi qua một mô hình suy luận đa bước thông qua các sơ đồ trực quan (Visualization) của **Chain-of-Thought** và **Tree-of-Thoughts**.
* Hiểu rõ chi tiết một luồng kiến trúc (Architecture Flow) thực tế trên môi trường AWS từ khi Client gửi request đến lúc nhận về kết quả từ Model.

Ứng dụng công cụ hiện đại

* Trực tiếp tìm hiểu về ý tưởng **Proptimizer**, một tiện ích thông minh có thể giúp bản thân tối ưu hóa các prompt và chat với AI ở mọi nơi trên không gian web.
* Nắm bắt sức mạnh của **Amazon Bedrock** trong việc hiện thực hóa các ý tưởng ứng dụng AI một cách nhanh chóng.

Kết nối và trao đổi

* Sự kiện đã cung cấp hệ quy chiếu chung giữa việc "thiết kế ứng dụng" (engineering) và "giao tiếp với mô hình" (prompting).
* Qua các ví dụ thực tiễn như prompt tối ưu lời giới thiệu cho thực tập sinh (Career coach), tôi nhận thấy prompt engineering rất gần gũi và có thể áp dụng lập tức vào bất cứ ngành nghề nào.

## Bài học rút ra

* Kỹ năng thiết kế câu lệnh (Prompt Engineering) ngày nay chính là chìa khóa để giải phóng toàn bộ tiềm năng của AI; giao tiếp tốt với AI đồng nghĩa với việc tối ưu hóa hiệu suất làm việc.
* Việc áp dụng các kiến trúc Serverless trên AWS để làm sản phẩm AI đem lại lợi ích tuyệt vời về chi phí khởi tạo (\$0) và độ linh hoạt cực cao

#### Một số hình ảnh khi tham gia sự kiện

* Thêm các hình ảnh của các bạn tại đây

> Tổng thể, sự kiện không chỉ cung cấp kiến thức kỹ thuật mà còn giúp tôi thay đổi cách tư duy về thiết kế ứng dụng, hiện đại hóa hệ thống và phối hợp hiệu quả hơn giữa các team.
