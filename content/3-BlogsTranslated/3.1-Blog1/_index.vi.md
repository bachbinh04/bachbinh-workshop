---


---
title: "Tự động hóa UI với Amazon Nova Act"
date: 2026-06-05
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
----------------------

# Tự động hóa UI với Amazon Nova Act

Việc tự động hóa các thao tác trên trình duyệt đã trở thành một phần quan trọng trong quá trình phát triển phần mềm. Những công việc như kiểm thử giao diện (UI Testing), thu thập dữ liệu (Web Scraping) hay tự động hóa các quy trình văn phòng đều yêu cầu trình duyệt thực hiện chính xác các thao tác của người dùng.

Trong nhiều năm, các framework như Selenium, Playwright hay Puppeteer đã trở thành lựa chọn phổ biến. Tuy nhiên, các công cụ này phụ thuộc rất nhiều vào XPath hoặc CSS Selector để xác định phần tử trên trang web. Khi giao diện thay đổi, các selector thường không còn hợp lệ, dẫn đến việc phải sửa lại toàn bộ script automation.

Amazon Nova Act được phát triển nhằm giải quyết hạn chế này bằng cách ứng dụng Agentic AI để điều khiển trình duyệt thông qua ngôn ngữ tự nhiên thay vì phụ thuộc vào cấu trúc HTML.

---

# Những hạn chế của Web Automation truyền thống

Các framework automation hiện nay hoạt động dựa trên việc xác định chính xác vị trí của từng thành phần trên giao diện.

Ví dụ:

- Click vào nút đăng nhập.
- Nhập dữ liệu vào ô tìm kiếm.
- Chọn một menu cụ thể.

Để thực hiện được điều này, lập trình viên phải sử dụng:

- XPath
- CSS Selector
- ID
- Name

Nhược điểm của phương pháp này là:

- Chỉ cần Front-end thay đổi cấu trúc HTML hoặc đổi tên class là toàn bộ script có thể bị lỗi.
- Chi phí bảo trì automation ngày càng lớn khi giao diện thay đổi liên tục.
- Việc xây dựng các workflow dài trở nên khó mở rộng.

---

# Amazon Nova Act là gì?

Amazon Nova Act là một dịch vụ AI Agent trên AWS giúp điều khiển trình duyệt web bằng ngôn ngữ tự nhiên.

Thay vì chỉ định chính xác XPath hoặc CSS Selector, người dùng chỉ cần mô tả hành động mong muốn bằng tiếng Anh.

Ví dụ:

```python
nova.act("Type 'iPhone' into the search bar and press Enter")
```

Nova Act sẽ tự động:

- Xác định ô tìm kiếm.
- Nhập dữ liệu.
- Thực hiện thao tác Enter.

Quá trình này không phụ thuộc trực tiếp vào HTML của trang web mà dựa trên khả năng hiểu giao diện của mô hình AI.

---

# Cách Nova Act hoạt động

Nova Act được xây dựng trên nền tảng Amazon Nova 2 Lite và được huấn luyện bằng Reinforcement Learning trong các môi trường mô phỏng trình duyệt (Web Gyms).

Thay vì nhận diện phần tử bằng XPath, AI sẽ phân tích:

- Giao diện trực quan.
- Bố cục của website.
- Ngữ cảnh của các thành phần.
- Nội dung hiển thị trên màn hình.

Nhờ đó, khi giao diện thay đổi nhỏ, workflow vẫn có khả năng tiếp tục hoạt động mà không cần chỉnh sửa code.

---

# Quy trình sử dụng Amazon Nova Act

## Bước 1: Thử nghiệm trên Playground

Amazon cung cấp một Playground cho phép người dùng trải nghiệm Nova Act trực tiếp trên trình duyệt.

Người dùng chỉ cần:

- nhập URL của website;
- mô tả yêu cầu bằng ngôn ngữ tự nhiên.

AI sẽ tự động:

- mở trang web;
- cuộn trang;
- di chuyển chuột;
- click;
- nhập dữ liệu.

Điều này giúp kiểm tra nhanh workflow mà không cần viết code.

---

## Bước 2: Phát triển bằng Python SDK

Sau khi thử nghiệm thành công, có thể sử dụng SDK Python để xây dựng workflow hoàn chỉnh.

Cài đặt:

```bash
pip install nova-act
```

Ví dụ:

```python
for customer in customer_list:
    nova.act(
        f"Fill name {customer['name']} and email {customer['email']} into register form"
    )

    nova.act(
        "Click Submit button and wait page reload"
    )
```

Trong ví dụ trên:

- Python xử lý dữ liệu từ danh sách khách hàng.
- Nova Act chịu trách nhiệm thao tác trên giao diện web.

Điều này cho phép kết hợp AI với toàn bộ logic của chương trình.

---

## Bước 3: Triển khai lên AWS

Sau khi hoàn thành workflow, Nova Act hỗ trợ triển khai trực tiếp lên hạ tầng AWS.

Quá trình triển khai bao gồm:

- đóng gói ứng dụng thành container;
- lưu trữ image trên Amazon ECR;
- chạy workflow trên Bedrock AgentCore;
- khởi tạo browser sandbox riêng cho từng phiên làm việc.

Việc này giúp mở rộng số lượng workflow mà không cần tự quản lý trình duyệt hoặc máy chủ.

---

# Các tính năng nổi bật

## Human-in-the-Loop (HITL)

Trong quá trình chạy automation, AI có thể gặp các tình huống như:

- CAPTCHA
- MFA
- tài khoản bị khóa

Thay vì dừng toàn bộ workflow, Nova Act sẽ gửi thông báo cho quản trị viên thông qua Amazon SNS.

Người dùng chỉ cần xử lý bước xác thực bằng tay, sau đó workflow sẽ tiếp tục thực hiện các bước còn lại.

---

## Observability

Nova Act cung cấp khả năng giám sát toàn bộ quá trình thực thi.

Người dùng có thể xem lại:

- video quá trình automation;
- ảnh chụp từng bước;
- lịch sử workflow.

Điều này giúp việc debug trở nên trực quan hơn so với các framework automation truyền thống.

---

## Enterprise Security

Toàn bộ workflow được thực thi trong môi trường sandbox của AWS.

Ngoài ra, Nova Act còn hỗ trợ:

- phân quyền bằng IAM;
- cô lập phiên làm việc;
- bảo vệ cookie và session;
- hạn chế rò rỉ dữ liệu.

Nhờ đó, giải pháp phù hợp với các môi trường doanh nghiệp yêu cầu mức bảo mật cao.

---

# Khi nào nên sử dụng Nova Act?

Nova Act phù hợp với các bài toán như:

- UI Automation Testing
- Web Automation
- Web Scraping
- Tự động điền biểu mẫu
- Xử lý các tác vụ văn phòng lặp đi lặp lại
- Xây dựng AI Agent thao tác trên trình duyệt

Đặc biệt, Nova Act phát huy hiệu quả trong các dự án có giao diện thường xuyên thay đổi.

---

# Kết luận

Amazon Nova Act mang đến một cách tiếp cận mới cho bài toán tự động hóa giao diện web bằng cách kết hợp AI Agent với trình duyệt.

Thay vì phụ thuộc hoàn toàn vào XPath hoặc CSS Selector, Nova Act cho phép lập trình viên mô tả hành động bằng ngôn ngữ tự nhiên, từ đó giảm đáng kể chi phí bảo trì script khi giao diện thay đổi.

Mặc dù Selenium và Playwright vẫn là những công cụ rất mạnh trong nhiều trường hợp, Nova Act mở ra một hướng tiếp cận mới cho các workflow cần khả năng thích nghi cao và tích hợp sâu với hệ sinh thái AWS. Đây là một lựa chọn đáng cân nhắc đối với các nhóm QA, DevOps và các doanh nghiệp đang xây dựng các hệ thống tự động hóa dựa trên AI.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Bắt đầu với healthcare data lakes: Sử dụng microservices

Các data lake có thể giúp các bệnh viện và cơ sở y tế chuyển dữ liệu thành những thông tin chi tiết về doanh nghiệp và duy trì hoạt động kinh doanh liên tục, đồng thời bảo vệ quyền riêng tư của bệnh nhân. **Data lake** là một kho lưu trữ tập trung, được quản lý và bảo mật để lưu trữ tất cả dữ liệu của bạn, cả ở dạng ban đầu và đã xử lý để phân tích. data lake cho phép bạn chia nhỏ các kho chứa dữ liệu và kết hợp các loại phân tích khác nhau để có được thông tin chi tiết và đưa ra các quyết định kinh doanh tốt hơn.

Bài đăng trên blog này là một phần của loạt bài lớn hơn về việc bắt đầu cài đặt data lake dành cho lĩnh vực y tế. Trong bài đăng blog cuối cùng của tôi trong loạt bài, *“Bắt đầu với data lake dành cho lĩnh vực y tế: Đào sâu vào Amazon Cognito”*, tôi tập trung vào các chi tiết cụ thể của việc sử dụng Amazon Cognito và Attribute Based Access Control (ABAC) để xác thực và ủy quyền người dùng trong giải pháp data lake y tế. Trong blog này, tôi trình bày chi tiết cách giải pháp đã phát triển ở cấp độ cơ bản, bao gồm các quyết định thiết kế mà tôi đã đưa ra và các tính năng bổ sung được sử dụng. Bạn có thể truy cập các code samples cho giải pháp tại Git repo này để tham khảo.

---

## Hướng dẫn kiến trúc

Thay đổi chính kể từ lần trình bày cuối cùng của kiến trúc tổng thể là việc tách dịch vụ đơn lẻ thành một tập hợp các dịch vụ nhỏ để cải thiện khả năng bảo trì và tính linh hoạt. Việc tích hợp một lượng lớn dữ liệu y tế khác nhau thường yêu cầu các trình kết nối chuyên biệt cho từng định dạng; bằng cách giữ chúng được đóng gói riêng biệt với microservices, chúng ta có thể thêm, xóa và sửa đổi từng trình kết nối mà không ảnh hưởng đến những kết nối khác. Các microservices được kết nối rời thông qua tin nhắn publish/subscribe tập trung trong cái mà tôi gọi là “pub/sub hub”.

Giải pháp này đại diện cho những gì tôi sẽ coi là một lần lặp nước rút hợp lý khác từ last post của tôi. Phạm vi vẫn được giới hạn trong việc nhập và phân tích cú pháp đơn giản của các **HL7v2 messages** được định dạng theo **Quy tắc mã hóa 7 (ER7)** thông qua giao diện REST.

**Kiến trúc giải pháp bây giờ như sau:**

> *Hình 1. Kiến trúc tổng thể; những ô màu thể hiện những dịch vụ riêng biệt.*

---

Mặc dù thuật ngữ *microservices* có một số sự mơ hồ cố hữu, một số đặc điểm là chung:

- Chúng nhỏ, tự chủ, kết hợp rời rạc
- Có thể tái sử dụng, giao tiếp thông qua giao diện được xác định rõ
- Chuyên biệt để giải quyết một việc
- Thường được triển khai trong **event-driven architecture**

Khi xác định vị trí tạo ranh giới giữa các microservices, cần cân nhắc:

- **Nội tại**: công nghệ được sử dụng, hiệu suất, độ tin cậy, khả năng mở rộng
- **Bên ngoài**: chức năng phụ thuộc, tần suất thay đổi, khả năng tái sử dụng
- **Con người**: quyền sở hữu nhóm, quản lý *cognitive load*

---

## Lựa chọn công nghệ và phạm vi giao tiếp


| Phạm vi giao tiếp                           | Các công nghệ / mô hình cần xem xét                                                 |
| --------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Trong một microservice                       | Amazon Simple Queue Service (Amazon SQS), AWS Step Functions                               |
| Giữa các microservices trong một dịch vụ | AWS CloudFormation cross-stack references, Amazon Simple Notification Service (Amazon SNS) |
| Giữa các dịch vụ                          | Amazon EventBridge, AWS Cloud Map, Amazon API Gateway                                      |

---

## The pub/sub hub

Việc sử dụng kiến trúc **hub-and-spoke** (hay message broker) hoạt động tốt với một số lượng nhỏ các microservices liên quan chặt chẽ.

- Mỗi microservice chỉ phụ thuộc vào *hub*
- Kết nối giữa các microservice chỉ giới hạn ở nội dung của message được xuất
- Giảm số lượng synchronous calls vì pub/sub là *push* không đồng bộ một chiều

Nhược điểm: cần **phối hợp và giám sát** để tránh microservice xử lý nhầm message.

---

## Core microservice

Cung cấp dữ liệu nền tảng và lớp truyền thông, gồm:

- **Amazon S3** bucket cho dữ liệu
- **Amazon DynamoDB** cho danh mục dữ liệu
- **AWS Lambda** để ghi message vào data lake và danh mục
- **Amazon SNS** topic làm *hub*
- **Amazon S3** bucket cho artifacts như mã Lambda

> Chỉ cho phép truy cập ghi gián tiếp vào data lake qua hàm Lambda → đảm bảo nhất quán.

---

## Front door microservice

- Cung cấp API Gateway để tương tác REST bên ngoài
- Xác thực & ủy quyền dựa trên **OIDC** thông qua **Amazon Cognito**
- Cơ chế *deduplication* tự quản lý bằng DynamoDB thay vì SNS FIFO vì:
  1. SNS deduplication TTL chỉ 5 phút
  2. SNS FIFO yêu cầu SQS FIFO
  3. Chủ động báo cho sender biết message là bản sao

---

## Staging ER7 microservice

- Lambda “trigger” đăng ký với pub/sub hub, lọc message theo attribute
- Step Functions Express Workflow để chuyển ER7 → JSON
- Hai Lambda:
  1. Sửa format ER7 (newline, carriage return)
  2. Parsing logic
- Kết quả hoặc lỗi được đẩy lại vào pub/sub hub

---

## Tính năng mới trong giải pháp

### 1. AWS CloudFormation cross-stack references

Ví dụ *outputs* trong core microservice:

```yaml
Outputs:
  Bucket:
    Value: !Ref Bucket
    Export:
      Name: !Sub ${AWS::StackName}-Bucket
  ArtifactBucket:
    Value: !Ref ArtifactBucket
    Export:
      Name: !Sub ${AWS::StackName}-ArtifactBucket
  Topic:
    Value: !Ref Topic
    Export:
      Name: !Sub ${AWS::StackName}-Topic
  Catalog:
    Value: !Ref Catalog
    Export:
      Name: !Sub ${AWS::StackName}-Catalog
  CatalogArn:
    Value: !GetAtt Catalog.Arn
    Export:
      Name: !Sub ${AWS::StackName}-CatalogArn
```
