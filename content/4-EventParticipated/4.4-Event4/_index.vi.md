---
title: "Event 4"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---
# BÀI THU HOẠCH: GIẢI PHÁP ĐẶT HÀNG QUA HỘI THOẠI AI (AI-POWERED CONVERSATIONAL ORDERING)

### Mục Đích Của Dự Án

* **Giải quyết rào cản của việc chuyển đổi ứng dụng (app switch):** Khách hàng thường mất hứng thú khi phải thoát khỏi luồng trò chuyện hiện tại để tải một app mới, đăng nhập và tạo tài khoản chỉ để đặt đồ ăn.
* **Khắc phục các lỗi "ảo giác" (hallucination) của AI đời cũ:** Lấy bài học từ thất bại của hệ thống AI McDonald's khi nhận diện sai ý định và đặt nhầm hàng trăm miếng gà cho khách hàng.
* **Xây dựng trợ lý AI đặt hàng đa kênh:** Đưa AI đặt hàng lên các ứng dụng nhắn tin quen thuộc (như Zalo, WhatsApp) mượt mà, giúp khách hàng đặt đồ ăn ngay trong lúc nhắn tin tự nhiên.

## Danh Sách Diễn Giả

* Các thành viên của đội **One Team** - Đội xuất sắc giành **Giải Nhất (First Prize)** tại sự kiện FCAJ x Agentic AI Build Week.

## Nội Dung Nổi Bật

### Vấn đề của các hệ thống đặt hàng hiện hành

* Các ứng dụng truyền thống có menu phức tạp, nhồi nhét nhiều quảng cáo khiến khách hàng tốn thời gian làm quen.
* AI đời cũ không hiểu được bản chất của giao tiếp tự nhiên (natural conversation), dễ ghi nhận sai đơn hàng khi khách hàng bất ngờ thay đổi ý định vào phút chót.

### Giải pháp Đặt hàng bằng AI (Conversational Ordering)

* **Không ma sát (Zero friction):** Khách hàng chat trực tiếp với thương hiệu (ví dụ KFC) qua nền tảng quen thuộc như Zalo. Không cần tải app, không cần luồng tạo tài khoản mới.
* **Cơ chế hoạt động:** AI sẽ tự động phân tích ý định (intent) của khách, hỏi đáp để làm rõ yêu cầu, tự động thêm món vào giỏ hàng và gợi ý áp dụng mã khuyến mãi.

### Kiến trúc hệ thống linh hoạt và tiết kiệm

* **Tách biệt logic bằng Adapter:** Sử dụng "Channel Adapter" để tiếp nhận tin nhắn từ nhiều kênh khác nhau, sau đó chuẩn hóa (Normalize message) trước khi đưa vào lõi AI. Nhờ đó, có thể mở rộng sang các nền tảng khác (như Jollibee, Facebook) mà không cần đập đi xây lại hệ thống.
* **Sức mạnh của Agent Core:** Đội không dùng Lambda thuần túy mà sử dụng Amazon Bedrock Agent Core vì dịch vụ này có Bộ nhớ (Memory). Nó có thể nhớ được lịch sử đặt hàng của tuần trước để phục vụ khách hàng tốt hơn.
* **Chi phí cực thấp:** Hệ thống chỉ mất 3-5 giây độ trễ và tiêu tốn khoảng 0.006 USD cho mỗi đơn hàng nhờ kiến trúc Serverless, giảm được tới 60% chi phí hạ tầng thông thường.

## Những Gì Học Được

### Tư Duy Thiết Kế (Business-First)

* **Luôn có cơ chế kiểm chứng (Verify):** AI lấy đơn nhưng luôn phải gửi bảng tóm tắt để khách hàng xác nhận lại cuối cùng, tránh trường hợp gửi nhầm đồ khách không muốn.
* **Human in the loop (Con người trong vòng lặp):** Giải pháp không bỏ rơi yếu tố con người. Đội đã thiết kế một Dashboard (bảng điều khiển) dành cho nhân viên nhà hàng để theo dõi lịch sử chat của AI và can thiệp xử lý ngay khi có lỗi xảy ra.

### Kiến Trúc Kỹ Thuật

* Việc sử dụng công cụ bên thứ ba như Tiny Fish để cào (scrape) dữ liệu tự động từ website chính thức của KFC giúp AI luôn có menu cập nhật nhất mà không cần API trực tiếp từ thương hiệu.
* Hiểu được vai trò của tường lửa WAF ở lớp đầu tiên (ingress layer) nhằm bảo vệ traffic của hệ thống khi có lượng lớn người dùng đổ vào cùng lúc.

### Bài Học Từ Hackathon (Teamwork)

* **Sức mạnh của sự đa dạng:** Đội gồm 5 người hoàn toàn không quen biết nhau trước đó, với nhiều rào cản ngôn ngữ (tiếng Anh giọng Ấn, giọng Mỹ, và có thành viên không nói tiếng Anh) nhưng vẫn kết nối và làm việc cực kỳ hiệu quả.
* Để giành chiến thắng, ngoài code giỏi, nhóm đã phải chịu áp lực cực lớn về mặt thời gian để vẽ được Sơ đồ kiến trúc (Architecture Diagram) thật dễ hiểu nhằm thuyết phục ban giám khảo trong vòng chỉ vài phút trình bày.

### Ứng Dụng Vào Công Việc

* **Áp dụng mô hình có Memory:** Nghiên cứu tích hợp Agent Core vào các dự án chatbot nội bộ để hệ thống giữ được mạch ngữ cảnh (context) dài hạn thay vì bị "mất trí nhớ" sau mỗi phiên chat.
* **Sử dụng kiến trúc Adapter:** Khi thiết kế các hệ thống phải kết nối nhiều nguồn đầu vào, sẽ áp dụng Adapter Pattern để chuẩn hóa dữ liệu, giúp dự án dễ dàng scale-up (mở rộng) sau này mà không ảnh hưởng tới Core Logic.
* **Phát triển mindset về sản phẩm:** Không chỉ mải mê code tính năng AI, luôn phải xây dựng thêm các công cụ giám sát (Dashboard) cho đội ngũ vận hành (Staff/Admin) để hệ thống thực sự mang lại giá trị cho doanh nghiệp.

## Trải nghiệm trong event

### Học hỏi từ các đội thi xuất sắc

* Lắng nghe phần pitching của quán quân giúp tôi nhận ra rằng: Một ý tưởng tốt không phải là nhồi nhét quá nhiều công nghệ phức tạp, mà là bắt đúng "nỗi đau" (pain point) của người dùng thực tế (sự phiền toái khi tải app mới).
* Việc phân tích rõ sự thất bại của các công ty lớn (McDonald's) làm tiền đề cho giải pháp của mình là một kỹ năng thuyết trình và kêu gọi vốn (pitching) cực kỳ sắc bén.

### Trải nghiệm kỹ thuật thực tế

* Thấy rõ được luồng hoạt động mượt mà của một hệ thống Multi-channel tích hợp Generative AI. Nhận thức được rằng AI không chỉ đóng vai trò hỏi đáp (chat) mà còn trực tiếp kích hoạt các hành động (Actions/Tools) như thêm vào giỏ hàng hay áp dụng mã giảm giá.

### Kết nối và tinh thần Hackathon

* Không khí của sự kiện vô cùng truyền cảm hứng. Hình ảnh các lập trình viên thức trắng đêm tới 3-4h sáng, uống Redbull, ngủ vật vờ dưới đất nhưng vẫn hoàn thành xuất sắc hệ thống đã cho thấy tinh thần khởi nghiệp và khả năng vượt qua giới hạn của các kỹ sư trẻ.
* Sự kiện khẳng định mạnh mẽ thông điệp: Trong kỷ nguyên AI, điều quan trọng nhất không chỉ là kiến thức cá nhân mà là khả năng "Roll together" - hợp tác, hạ cái tôi xuống để build sản phẩm chung.

#### Một số hình ảnh khi tham gia sự kiện

* Thêm các hình ảnh của các bạn tại đây
* ![alt text](/images/4-EventParticipated/4.4-Event4/image.jpg)
* ![alt text](/images/4-EventParticipated/4.4-Event4/IMG.png)

> Tổng thể, Event 4 đã mang lại nhiều góc nhìn thực tiễn và cảm hứng sáng tạo mạnh mẽ thông qua dự án quán quân Giải Nhất AI-Powered Conversational Ordering của đội One Team.
