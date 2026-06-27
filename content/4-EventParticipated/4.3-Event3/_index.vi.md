---
title: "Event 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.3. </b> "
---
# Bài thu hoạch XÂY DỰNG TRỢ LÝ GIỌNG NÓI AI (VOICE AGENTS) QUY MÔ LỚN

### Mục Đích Của Sự Kiện

* Giới thiệu tổng quan về cơ chế hoạt động của Voice AI và cách cung cấp khả năng giao tiếp bằng giọng nói cho các hệ thống trí tuệ nhân tạo.
* Phân tích các giới hạn của AI giọng nói hiện tại đối với tiếng Việt và cách giải quyết bài toán xử lý ngôn ngữ trong môi trường doanh nghiệp (đặc biệt là khối ngân hàng).
* Khám phá các tiêu chuẩn kiến trúc để đưa một Voice Agent từ môi trường thử nghiệm (POC) lên môi trường thực tế (Production).
* Truyền cảm hứng cho việc phát triển các trải nghiệm giao tiếp giữa người và máy tính một cách tự nhiên, mượt mà và bảo mật.

## Danh Sách Diễn Giả

* **Hiếu Nghị**
* **Kiệt**
* **Trung Đỗ**

## Nội Dung Nổi Bật


* **Lựa chọn kiến trúc AI phù hợp với ngôn ngữ**
  * Các mô hình Speech-to-Speech hiện tại đa phần chỉ tối ưu cho tiếng Anh. Tiếng Việt là ngôn ngữ ít tài nguyên (low-resource language), nên để vận hành hiệu quả, kiến trúc hệ thống được tách thành 3 phần: Speech-to-Text (STT) -> LLM xử lý văn bản -> Text-to-Speech (TTS).
  * Kiến trúc này giúp doanh nghiệp kiểm soát chặt chẽ câu trả lời của AI (tránh AI nói linh tinh) và dễ dàng thực thi các tác vụ phức tạp (Tool calling) như tự động khóa thẻ ngân hàng.
* **Xử lý ngữ cảnh và văn hóa giao tiếp (Context & Culture)**
  * Hệ thống cần khả năng nhận diện giới tính từ giọng nói để xưng hô (anh/chị) một cách chính xác.
  * Xử lý bài toán "ngắt lời": AI phải được huấn luyện để phân biệt được khi nào người dùng đang ngừng lại suy nghĩ (VD: ngắt quãng khi đọc số điện thoại) và khi nào đã nói xong, tránh tình trạng "nhảy vào miệng" khách hàng.
  * Với giọng vùng miền (accent), dữ liệu huấn luyện STT cần có 10-20% là giọng địa phương để nhận diện tốt thông tin. Tuy nhiên, AI phản hồi vẫn nên giữ giọng chuẩn, trừ những use case đặc thù như sale hoặc nhắc nợ.
* **Tối ưu tốc độ và đưa lên Production**
  * Tốc độ phản hồi (Latency) là yếu tố sống còn. Quá trình xử lý âm thanh, văn bản và LLM phải được thực hiện thông qua cơ chế *streaming* (luồng dữ liệu liên tục) để giảm thiểu độ trễ.
  * Phải có cơ chế *Human-in-the-loop*: Hệ thống cần nhận diện được khi nào AI quá giới hạn (VD: khách hàng đang cáu gắt) để chuyển tiếp cuộc gọi mượt mà sang nhân viên con người.

## Những Gì Học Được


* **Tư Duy Thiết Kế**
  * Sản phẩm AI tốt không chỉ nằm ở công nghệ lõi mà phải xoay quanh trải nghiệm, thấu hiểu hành vi và văn hóa giao tiếp tự nhiên của con người.
  * Khi thiết kế hệ thống tự động hóa, luôn phải chừa "đường lùi" mượt mà (chuyển giao cho người thật), không phó mặc 100% cho AI ở những điểm chạm nhạy cảm với khách hàng.
* **Kiến Trúc Kỹ Thuật**
  * Nắm vững sự ưu việt của mô hình phân rã 3 thành phần (STT - LLM - TTS) khi giải quyết các bài toán ngôn ngữ đặc thù.
  * Hiểu rõ vai trò bắt buộc của cơ chế streaming và tool calling trong việc biến AI từ một chatbot hỏi - đáp thuần túy thành một "agent" chủ động thao tác theo thời gian thực.
* **Ứng Dụng Vào Công Việc**
  * Nâng cấp trải nghiệm ứng dụng: Vận dụng tư duy chia tách kiến trúc STT-LLM-TTS để tích hợp trợ lý điều khiển bằng giọng nói vào các ứng dụng di động đa nền tảng (như Flutter) kết nối với backend, giúp mở rộng khả năng tương tác rảnh tay cho người dùng cuối.
  * Tối ưu hóa hạ tầng đám mây: Ứng dụng các nguyên lý thiết kế tối ưu độ trễ và xử lý streaming vào việc phát triển hệ thống trên môi trường AWS, kết hợp linh hoạt những kiến thức nền tảng về cloud để xây dựng các flow tự động hóa tốc độ cao và chịu tải tốt.

## Trải nghiệm trong event


* **Học hỏi từ chuyên gia thực chiến**
  * Sự chia sẻ từ các founder và kỹ sư mang tới góc nhìn sâu sắc về khoảng cách giữa việc làm một bản demo AI đơn giản và việc xây dựng một hệ thống vận hành thực tế (production) phục vụ hàng triệu người dùng tại các ngân hàng lớn.
* **Trải nghiệm kỹ thuật thực tế**
  * Được trực tiếp theo dõi live demo mượt mà của hệ thống Voice Agent, đồng thời hiểu rõ hơn về cách các kỹ sư đối mặt và giải quyết những "pain point" cực kỳ hóc búa của tiếng Việt.
  * Mở rộng tầm nhìn về tiềm năng của các hệ thống AI thế hệ mới khi được trao quyền thực thi tác vụ trực tiếp thông qua Tool calling, thay vì chỉ cung cấp thông tin thụ động.

## Bài học rút ra

*
* Kiến trúc phân rã (STT - LLM - TTS) kết hợp khả năng gọi hàm (Tool Calling) là giải pháp tối ưu để vượt qua rào cản tài nguyên của tiếng Việt và biến AI thành "người thực thi" tác vụ.
* Trải nghiệm giao tiếp thấu hiểu văn hóa (xưng hô chuẩn xác, ngắt nghỉ tự nhiên) và cơ chế dự phòng chuyển giao cho con người (Human-in-the-loop) là yếu tố sống còn để đưa Voice AI vào vận hành thực tế.

#### Một số hình ảnh khi tham gia sự kiện

* Thêm các hình ảnh của các bạn tại đây

> Tổng thể, sự kiện không chỉ cung cấp kiến thức kỹ thuật mà còn giúp tôi thay đổi cách tư duy về thiết kế ứng dụng, hiện đại hóa hệ thống và phối hợp hiệu quả hơn giữa các team.
