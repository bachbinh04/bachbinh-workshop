---
title: "Event 4"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---
# BÀI THU HOẠCH: BÁO CÁO CÁC DỰ ÁN TRONG EVENT 4

### Mục Đích Của Sự Kiện

* Tổng kết và lắng nghe phần trình bày sản phẩm, giải pháp AI thực tế từ các nhóm phát triển.
* Khám phá ứng dụng đa dạng của AI/LLM, Computer Vision, Multi-agent Systems và hạ tầng Cloud trong nhiều lĩnh vực: F&B, Phân tích chiến lược doanh nghiệp, Giải pháp kiến trúc SA, Giám sát an ninh/ùn tắc, và Phòng chống rửa tiền (AML).
* Học hỏi kinh nghiệm thực chiến về quy trình thiết kế, đóng gói sản phẩm và giải quyết bài toán nghiệp vụ phức tạp từ các đội thi.

## Danh Sách Các Đội Thi & Đề Tài Dự Án

### 1. Team One Team

* **Chủ đề:** AI-powered Conversational Ordering (Trợ lý AI đặt hàng qua hội thoại).
* **Mô tả dự án:** Dự án xây dựng một chatbot AI đa kênh (như Zalo, WhatsApp) cho phép khách hàng đặt đồ ăn (ví dụ mô phỏng cho thương hiệu KFC) trực tiếp qua tin nhắn một cách tự nhiên mà không cần tải app hay tạo tài khoản mới.

### 2. Team Signal Scout (tên cũ: Dream AI)

* **Chủ đề:** Hệ thống Multi-agent phân tích chiến lược kinh doanh.
* **Mô tả dự án:** Giải pháp thu thập và xâu chuỗi các dữ liệu rời rạc của công ty đối thủ. Từ đó, AI giúp các nhà hoạch định chiến lược phân tích, đánh giá rủi ro và dự báo tỷ suất hoàn vốn (ROI) nếu doanh nghiệp áp dụng cấu trúc/chiến lược của đối thủ.

### 3. Team Plan (hoặc Team BL)

* **Chủ đề:** SA Professional AI Native App (Trợ lý AI cho Solution Architect).
* **Mô tả dự án:** Một ứng dụng giúp các kỹ sư giải pháp (SA) phân tích yêu cầu bằng ngôn ngữ tự nhiên hoặc tài liệu văn bản để tự động vẽ sơ đồ kiến trúc hệ thống, xuất bảng tính chi phí và tự động tạo mã cơ sở hạ tầng (như Terraform).

### 4. Team 3K

* **Chủ đề:** Sheper (Hệ thống AI Camera chống ùn tắc).
* **Mô tả dự án:** Dự án ứng dụng Computer Vision (YOLO) và AI theo thời gian thực để giám sát luồng người. Hệ thống giúp phát hiện, cảnh báo và tự động điều phối nhân viên giải quyết tình trạng ùn tắc tại các khu vực đông người như sân bay hay siêu thị.

### 5. Team Six Pillar (Sixer)

* **Chủ đề:** Adaptive Workflow Engine (Giải pháp phòng chống rửa tiền - AML).
* **Mô tả dự án:** Hệ thống sử dụng kiến trúc Multi-agent hỗ trợ các ngân hàng và tổ chức tài chính. Trợ lý AI sẽ tự động điều tra các cảnh báo giao dịch đáng ngờ, phân tích dòng tiền, hồ sơ khách hàng để giảm thiểu tỷ lệ cảnh báo sai (false positive) và tự động tạo báo cáo bằng chứng cho chuyên viên.

## Nội Dung Nổi Bật

* **Tương tác hội thoại tự nhiên & Đa kênh:** Xu hướng đưa giải pháp AI tiếp cận trực tiếp kênh nhắn tin phổ biến (Zalo, WhatsApp) loại bỏ rào cản cài đặt app, mang lại trải nghiệm tiện lợi tối đa cho khách hàng F&B.
* **Sức mạnh của Multi-Agent Systems:** Ứng dụng kiến trúc Multi-agent trong việc phân tích thông tin chiến lược doanh nghiệp và tự động điều tra dòng tiền gian lận AML, giúp xử lý các bài toán nghiệp vụ phức tạp với độ chính xác cao.
* **Tự động hóa công việc cho Kỹ sư Giải pháp (SA):** Khả năng chuyển đổi từ yêu cầu ngôn ngữ tự nhiên sang sơ đồ kiến trúc, dự toán chi phí và sinh mã Infrastructure as Code (Terraform) giúp tăng tốc đáng kể quy trình tư vấn và triển khai hạ tầng đám mây.
* **Computer Vision trong xử lý thời gian thực:** Kết hợp mô hình YOLO với AI để phân tích mật độ đám đông, hỗ trợ vận hành và điều phối nhân sự kịp thời tại các địa điểm công cộng.

## Những Gì Học Được

### Tư Duy Thiết Kế

* Trọng tâm của giải pháp AI phải là giải quyết nỗi đau cụ thể của người dùng và doanh nghiệp (giảm friction khi đặt hàng, tự động hóa quy trình phân tích, giảm tỷ lệ cảnh báo sai trong ngân hàng).
* Tận dụng tối đa các nền tảng và kênh giao tiếp có sẵn thay vì bắt người dùng phải làm quen với công cụ mới.

### Kiến Trúc Kỹ Thuật

* Kiến trúc Multi-agent phối hợp nhiều agent chuyên biệt để giải quyết các luồng công việc phức tạp (như phân tích chiến lược hay điều tra AML).
* Tích hợp Computer Vision (YOLO) với hệ thống xử lý luồng sự kiện thời gian thực (Real-time Event Processing).
* Sinh mã tự động (IaC - Terraform) và sơ đồ kiến trúc trực quan dựa trên kết quả phân tích LLM.

### Ứng Dụng Vào Công Việc

* Áp dụng tư duy Multi-agent và AI Automation vào việc phát triển các dự án thực tế.
* Học hỏi cách thiết kế các giao tiếp conversational AI mượt mà và linh hoạt.

## Trải nghiệm trong event

* **Lắng nghe và giao lưu:** Được chứng kiến các phần trình bày chất lượng từ 5 đội thi với những góc nhìn công nghệ sắc bén và tính ứng dụng cao.
* **Mở rộng tầm nhìn:** Nhìn thấy tiềm năng vô hạn của GenAI và Computer Vision khi giải quyết các bài toán từ F&B, bán lẻ đến tài chính ngân hàng và tư vấn giải pháp.

## Bài học rút ra

* Kết hợp đúng công nghệ AI với bài toán thực tế sẽ tạo ra giá trị đột phá cho doanh nghiệp.
* Mô hình Multi-agent và tính năng tự động hóa bằng AI đang trở thành xu hướng cốt lõi trong xây dựng phần mềm hiện đại.

#### Một số hình ảnh khi tham gia sự kiện

* Thêm các hình ảnh của các bạn tại đây
* ![alt text](/images/4-EventParticipated/4.4-Event4/image.jpg)

> Tổng thể, Event 4 đã mang lại nhiều góc nhìn thực tiễn và cảm hứng sáng tạo mạnh mẽ thông qua các dự án đa dạng của 5 đội thi.
