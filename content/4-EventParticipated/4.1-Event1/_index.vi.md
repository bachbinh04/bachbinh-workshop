---
title: "Event 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---
# Bài thu hoạch Automated Prompt Engineering: Enhancing LLM Output Quality

### Mục Đích Của Sự Kiện

* Chia sẻ nghệ thuật giao tiếp với AI (The Art of Communicating with AI) và cách nâng cao chất lượng đầu ra của các Mô hình Ngôn ngữ Lớn (LLM).
* Chỉ ra tầm quan trọng của việc đặt câu lệnh (Prompt Engineering) và những ảnh hưởng tiêu cực của việc đặt câu lệnh sai cách.
* Cung cấp các cấu trúc, nguyên tắc và kỹ thuật từ cơ bản đến nâng cao để tương tác hiệu quả với LLM.
* Giới thiệu giải pháp "Proptimizer" - tự động hóa việc tối ưu prompt cùng với kiến trúc hệ thống chạy trên đám mây AWS.

Danh Sách Diễn Giả

* **Nguyễn Tuấn Thịnh** - DevOps/Cloud Engineer, First Cloud AI Journey.

Nội Dung Nổi Bật

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

Những Gì Học Được

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

Trải nghiệm trong event

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

Bài học rút ra

* Kỹ năng thiết kế câu lệnh (Prompt Engineering) ngày nay chính là chìa khóa để giải phóng toàn bộ tiềm năng của AI; giao tiếp tốt với AI đồng nghĩa với việc tối ưu hóa hiệu suất làm việc.
* Việc áp dụng các kiến trúc Serverless trên AWS để làm sản phẩm AI đem lại lợi ích tuyệt vời về chi phí khởi tạo (\$0) và độ linh hoạt cực ca

- Chia sẻ best practices trong thiết kế ứng dụng hiện đại
- Giới thiệu phương pháp DDD và event-driven architecture
- Hướng dẫn lựa chọn compute services phù hợp
- Giới thiệu công cụ AI hỗ trợ development lifecycle

### Danh Sách Diễn Giả

- **Jignesh Shah** - Director, Open Source Databases
- **Erica Liu** - Sr. GTM Specialist, AppMod
- **Fabrianne Effendi** - Assc. Specialist SA, Serverless Amazon Web Services

### Nội Dung Nổi Bật

#### Đưa ra các ảnh hưởng tiêu cực của kiến trúc ứng dụng cũ

- Thời gian release sản phẩm lâu → Mất doanh thu/bỏ lỡ cơ hội
- Hoạt động kém hiệu quả → Mất năng suất, tốn kém chi phí
- Không tuân thủ các quy định về bảo mật → Mất an ninh, uy tín

#### Chuyển đổi sang kiến trúc ứng dụng mới - Microservice Architecture

Chuyển đổi thành hệ thống modular – từng chức năng là một **dịch vụ độc lập** giao tiếp với nhau qua **sự kiện** với 3 trụ cột cốt lõi:

- **Queue Management**: Xử lý tác vụ bất đồng bộ
- **Caching Strategy:** Tối ưu performance
- **Message Handling:** Giao tiếp linh hoạt giữa services

#### Domain-Driven Design (DDD)

- **Phương pháp 4 bước**: Xác định domain events → sắp xếp timeline → identify actors → xác định bounded contexts
- **Case study bookstore**: Minh họa cách áp dụng DDD thực tế
- **Context mapping**: 7 patterns tích hợp bounded contexts

#### Event-Driven Architecture

- **3 patterns tích hợp**: Publish/Subscribe, Point-to-point, Streaming
- **Lợi ích**: Loose coupling, scalability, resilience
- **So sánh sync vs async**: Hiểu rõ trade-offs (sự đánh đổi)

#### Compute Evolution

- **Shared Responsibility Model**: Từ EC2 → ECS → Fargate → Lambda
- **Serverless benefits**: No server management, auto-scaling, pay-for-value
- **Functions vs Containers**: Criteria lựa chọn phù hợp

#### Amazon Q Developer

- **SDLC automation**: Từ planning đến maintenance
- **Code transformation**: Java upgrade, .NET modernization
- **AWS Transform agents**: VMware, Mainframe, .NET migration

### Những Gì Học Được

#### Tư Duy Thiết Kế

- **Business-first approach**: Luôn bắt đầu từ business domain, không phải technology
- **Ubiquitous language**: Importance của common vocabulary giữa business và tech teams
- **Bounded contexts**: Cách identify và manage complexity trong large systems

#### Kiến Trúc Kỹ Thuật

- **Event storming technique**: Phương pháp thực tế để mô hình hóa quy trình kinh doanh
- Sử dụng **Event-driven communication** thay vì synchronous calls
- **Integration patterns**: Hiểu khi nào dùng sync, async, pub/sub, streaming
- **Compute spectrum**: Criteria chọn từ VM → containers → serverless

#### Chiến Lược Hiện Đại Hóa

- **Phased approach**: Không rush, phải có roadmap rõ ràng
- **7Rs framework**: Nhiều con đường khác nhau tùy thuộc vào đặc điểm của mỗi ứng dụng
- **ROI measurement**: Cost reduction + business agility

### Ứng Dụng Vào Công Việc

- **Áp dụng DDD** cho project hiện tại: Event storming sessions với business team
- **Refactor microservices**: Sử dụng bounded contexts để identify service boundaries
- **Implement event-driven patterns**: Thay thế một số sync calls bằng async messaging
- **Serverless adoption**: Pilot AWS Lambda cho một số use cases phù hợp
- **Try Amazon Q Developer**: Integrate vào development workflow để boost productivity

### Trải nghiệm trong event

Tham gia workshop **“GenAI-powered App-DB Modernization”** là một trải nghiệm rất bổ ích, giúp tôi có cái nhìn toàn diện về cách hiện đại hóa ứng dụng và cơ sở dữ liệu bằng các phương pháp và công cụ hiện đại. Một số trải nghiệm nổi bật:

#### Học hỏi từ các diễn giả có chuyên môn cao

- Các diễn giả đến từ AWS và các tổ chức công nghệ lớn đã chia sẻ **best practices** trong thiết kế ứng dụng hiện đại.
- Qua các case study thực tế, tôi hiểu rõ hơn cách áp dụng **Domain-Driven Design (DDD)** và **Event-Driven Architecture** vào các project lớn.

#### Trải nghiệm kỹ thuật thực tế

- Tham gia các phiên trình bày về **event storming** giúp tôi hình dung cách **mô hình hóa quy trình kinh doanh** thành các domain events.
- Học cách **phân tách microservices** và xác định **bounded contexts** để quản lý sự phức tạp của hệ thống lớn.
- Hiểu rõ trade-offs giữa **synchronous và asynchronous communication** cũng như các pattern tích hợp như **pub/sub, point-to-point, streaming**.

#### Ứng dụng công cụ hiện đại

- Trực tiếp tìm hiểu về **Amazon Q Developer**, công cụ AI hỗ trợ SDLC từ lập kế hoạch đến maintenance.
- Học cách **tự động hóa code transformation** và pilot serverless với **AWS Lambda**, từ đó nâng cao năng suất phát triển.

#### Kết nối và trao đổi

- Workshop tạo cơ hội trao đổi trực tiếp với các chuyên gia, đồng nghiệp và team business, giúp **nâng cao ngôn ngữ chung (ubiquitous language)** giữa business và tech.
- Qua các ví dụ thực tế, tôi nhận ra tầm quan trọng của **business-first approach**, luôn bắt đầu từ nhu cầu kinh doanh thay vì chỉ tập trung vào công nghệ.

#### Bài học rút ra

- Việc áp dụng DDD và event-driven patterns giúp giảm **coupling**, tăng **scalability** và **resilience** cho hệ thống.
- Chiến lược hiện đại hóa cần **phased approach** và đo lường **ROI**, không nên vội vàng chuyển đổi toàn bộ hệ thống.
- Các công cụ AI như Amazon Q Developer có thể **boost productivity** nếu được tích hợp vào workflow phát triển hiện tại.

#### Một số hình ảnh khi tham gia sự kiện

* Thêm các hình ảnh của các bạn tại đây

> Tổng thể, sự kiện không chỉ cung cấp kiến thức kỹ thuật mà còn giúp tôi thay đổi cách tư duy về thiết kế ứng dụng, hiện đại hóa hệ thống và phối hợp hiệu quả hơn giữa các team.
