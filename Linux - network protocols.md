---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 11
creation date: 2024-12-11 10:24
modification date: Wednesday 11th December 2024 10:24:43
---

#job/vietnix #linux #computerScience/networking 
## Article link:

[Site Unreachable](https://www.geeksforgeeks.org/types-of-network-protocols-and-their-uses/)
[14 Common Network Protocols and Their Functions Explained](https://www.techtarget.com/searchnetworking/feature/12-common-network-protocols-and-their-functions-explained)
[[Linux - What is DNS]]
[Voice over Internet Protocol (VoIP) - GeeksforGeeks](https://www.geeksforgeeks.org/voice-over-internet-protocol-voip/)
related notes: 
- [[]]
_____
## goal 

tìm hiểu các vấn đề cơ bản của 1 sysadmin hiều như: + DNS + HTTP/HTTPS + TCP/UDP/ICMP

1 số dịch vụ web/mail/ftp/imap & pop3/smtp 

cần hiều: 
- Nó chạy thông qua giao thức gì
- Port mặc định bao nhiêu 
- Điểm khác biệt giữa từng nhóm (ví dụ như http - https, tcp -udp, pop3 - imap)
-  Mỗi loại chạy trên ứng dụng gì


## protocols 

**Bảng so sánh các phương thức và dịch vụ thường gặp trong hệ thống**

| Phương thức/Dịch vụ | Giao thức          | Port mặc định                     | Điểm khác biệt chính                                                                                                                              | Ứng dụng điển hình                                                                                                                                         | tầng OSI |
| ------------------- | ------------------ | --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| **DNS**             | UDP (53), TCP (53) | 53                                | **Quy đổi tên miền thành địa chỉ IP.** Sử dụng UDP cho các truy vấn nhanh, TCP cho các truy vấn phức tạp hơn.                                     | Giải quyết tên miền khi bạn nhập địa chỉ website vào trình duyệt.                                                                                          | 7        |
| **HTTP**            | TCP                | 80                                | **Truyền tải dữ liệu văn bản (HTML, CSS, JS) trên web.** Không mã hóa dữ liệu, dễ bị tấn công.                                                    | Truy cập các trang web thông thường ([http://example.com](https://www.google.com/url?sa=E&source=gmail&q=http://example.com)).                             | 7        |
| **HTTPS**           | TCP                | 443                               | **Phiên bản bảo mật của HTTP.** Sử dụng SSL/TLS để mã hóa dữ liệu, bảo vệ thông tin người dùng.                                                   | Truy cập các trang web yêu cầu bảo mật ([https://example.com](https://www.google.com/url?sa=E&source=gmail&q=https://example.com)), thanh toán trực tuyến. | 7        |
| **TCP**             | -                  | Nhiều                             | **Giao thức truyền dữ liệu tin cậy, định hướng kết nối.** Đảm bảo dữ liệu được truyền đến đúng đích và theo thứ tự.                               | Phần lớn các dịch vụ mạng (HTTP, HTTPS, FTP, SSH, ...). SSL, TLS chạy trên TCP                                                                             | 4        |
| **UDP**             | -                  | Nhiều                             | **Giao thức truyền dữ liệu không tin cậy, không định hướng kết nối.** Tốc độ cao nhưng không đảm bảo dữ liệu được truyền đầy đủ hoặc theo thứ tự. | DNS, streaming media, VoIP.                                                                                                                                | 4        |
| **ICMP**            | IP                 | Nhiều                             | **Giao thức báo cáo lỗi và thông tin mạng.** Sử dụng để kiểm tra kết nối, ping, traceroute.                                                       | Ping, traceroute, kiểm tra kết nối.                                                                                                                        | 3        |
| **FTP**             | TCP                | 21 (control), 20 (data)           | **Truyền tệp tin.** Cho phép tải lên và tải xuống tệp tin qua mạng.                                                                               | Truyền tệp tin giữa các máy tính.                                                                                                                          | 7        |
| **IMAP**            | TCP                | 143 (không mã hóa), 993 (SSL/TLS) | **Truy cập email trên máy chủ.** Cho phép quản lý email trực tiếp trên máy chủ, đồng bộ hóa giữa nhiều thiết bị.                                  | Kiểm tra email trên nhiều thiết bị (điện thoại, máy tính bảng, ...).                                                                                       | 7        |
| **POP3**            | TCP                | 110 (không mã hóa), 995 (SSL/TLS) | **Truy cập email trên máy chủ.** Tải email về máy khách và xóa khỏi máy chủ.                                                                      | Kiểm tra email trên một thiết bị chính.                                                                                                                    | 7        |
| **SMTP**            | TCP                | 25 (không mã hóa), 587 (TLS)      | **Gửi email.** Sử dụng để gửi email từ một máy khách đến máy chủ thư.                                                                             | Gửi email.                                                                                                                                                 | 7        |
| **SSH**             | TCP                | 22                                | **Kết nối remote**                                                                                                                                | điều kiện, quản trị từ xa                                                                                                                                  | 7        |
| **VoiP**            | UDP                | nhiều                             | **truyền giọng nói**                                                                                                                              | viễn thông                                                                                                                                                 | 7        |

**Giải thích thêm:**

- **DNS:** Hệ thống tên miền, dịch tên miền dễ nhớ thành địa chỉ IP máy tính.
- **HTTP/HTTPS:** Giao thức truyền tải siêu văn bản, sử dụng để hiển thị các trang web. HTTPS là phiên bản bảo mật của HTTP.
- **TCP/UDP:** Giao thức truyền thông, TCP đảm bảo dữ liệu được truyền đầy đủ, UDP ưu tiên tốc độ.
- **ICMP:** Giao thức báo cáo lỗi và thông tin mạng, sử dụng để kiểm tra kết nối.
- **FTP:** Giao thức truyền tệp tin, cho phép tải lên và tải xuống tệp tin.
- **IMAP/POP3:** Giao thức truy cập email, IMAP cho phép quản lý email trực tiếp trên máy chủ, POP3 tải email về máy khách.
- **SMTP:** Giao thức gửi email.
- **port 3389** dùng để đăng nhập vào máy chủ windows 

### phân biệt các phương thức mail  

|Tính năng|POP3|IMAP|Exchange|
|---|---|---|---|
|**Khái niệm**|Post Office Protocol 3|Internet Message Access Protocol|Hệ thống email doanh nghiệp|
|**Cách hoạt động**|Tải email về máy tính và xóa khỏi máy chủ.|Để email trên máy chủ, đồng bộ hóa giữa các thiết bị.|Cung cấp dịch vụ email toàn diện cho doanh nghiệp, tích hợp với các ứng dụng khác.|
|**Truy cập email**|Chủ yếu trên một thiết bị.|Trên nhiều thiết bị.|Trên nhiều thiết bị, tích hợp với các ứng dụng văn phòng.|
|**Quản lý email**|Chủ yếu trên máy tính.|Trên máy chủ và máy tính.|Trên máy chủ và các ứng dụng khách.|
|**Đồng bộ hóa**|Không đồng bộ.|Đồng bộ hóa cao.|Đồng bộ hóa cao, tích hợp với lịch, danh bạ.|
|**Dung lượng lưu trữ**|Giới hạn bởi dung lượng máy tính.|Giới hạn bởi dung lượng máy chủ.|Dung lượng lớn, có thể tùy chỉnh.|
|**Bảo mật**|Tùy thuộc vào phần mềm email.|Tùy thuộc vào máy chủ email.|Bảo mật cao, có các tính năng bảo mật nâng cao.|
|**Tính năng bổ sung**|Ít tính năng.|Nhiều tính năng quản lý thư mục, tìm kiếm.|Tích hợp với lịch, danh bạ, chia sẻ tệp, hội nghị trực tuyến.|
|**Sử dụng cho**|Người dùng cá nhân, ít thiết bị.|Người dùng muốn truy cập email trên nhiều thiết bị.|Doanh nghiệp, tổ chức.|

### Giải thích chi tiết:

- **POP3:**
    - **Ưu điểm:** Đơn giản, dễ sử dụng, tải email về máy tính để làm việc offline.
    - **Nhược điểm:** Chỉ truy cập được trên một thiết bị, không đồng bộ, nếu xóa email trên máy tính sẽ bị xóa luôn trên máy chủ.
- **IMAP:**
    - **Ưu điểm:** Đồng bộ hóa giữa các thiết bị, quản lý thư mục linh hoạt, truy cập email từ bất kỳ đâu có kết nối internet.
    - **Nhược điểm:** Cần kết nối internet ổn định, cấu hình phức tạp hơn POP3.
- **Exchange:**
    - **Ưu điểm:** Bảo mật cao, tích hợp với các ứng dụng văn phòng (Outlook, Word, Excel), nhiều tính năng quản lý email chuyên nghiệp.
    - **Nhược điểm:** Chi phí cao, cần cấu hình phức tạp.



### UDP vs TCP vs SCTP 

[[Linux - Payload, Head, Overhead and other concepts]]

| Protocol                  | TCP (Transmission Control Protocol)                                                         | UDP (User Datagram Protocol)                                       | SCTP (Stream Control Transmission Protocol)                                                 |
| ------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------- |
| Reliability               | Reliable data delivery with error detection, retransmission, and acknowledgement mechanisms | Unreliable data delivery without error recovery or acknowledgement | Reliable data delivery with error detection, retransmission, and acknowledgement mechanisms |
| Connection Type           | Connection-oriented                                                                         | Connectionless                                                     | Connection-oriented                                                                         |
| Ordering                  | Guarantees ordered delivery of data packets                                                 | Does not guarantee the ordered delivery of data packets            | Guarantees ordered delivery of data packets                                                 |
| Speed                     | Slower due to reliability mechanisms                                                        | Faster due to minimal overhead                                     | Comparable to TCP, slower than UDP due to additional functionality                          |
| Overhead                  | Higher overhead due to additional headers and control mechanisms                            | Lower overhead due to minimal headers and control mechanisms       | Moderate overhead due to additional headers and control mechanisms                          |
| Applications              | Web browsing, email transfer, file transfer (FTP)                                           | Real-time communication, video streaming, online gaming, DNS       | Telecommunications, voice and video over IP, signalling transport                           |
| Congestion Control        | Implements congestion control mechanisms to optimize network performance                    | No congestion control mechanisms                                   | Implements congestion control mechanisms to optimize network performance                    |
| Error Recovery            | Detects and retransmits lost or corrupted packets                                           | No error recovery mechanisms                                       | Detects and retransmits lost or corrupted packets                                           |
| Message-Oriented Delivery | No                                                                                          | No                                                                 | Yes, supports message-oriented delivery                                                     |
| Multi-streaming           | No                                                                                          | No                                                                 | Yes, supports the simultaneous transmission of multiple streams                             |
| Multi-homing              | No                                                                                          | No                                                                 | Yes, supports multiple IP addresses for fault tolerance and resilience                      |
|                           |                                                                                             |                                                                    |                                                                                             |

Một khi người dùng get một trang web: 
- trước tiên sẽ hỏi các host trong máy (/etc/hosts) -> nếu không có sẽ hỏi các DNS service ở bên ngoài 
 -> phân giải domain thành IP -> hỏi dns xem domain này trỏ đến ip nào bằng cách tìm các A record  
UDP: cho client tương tác với các dns resolver 
TCP: cho các máy chứa DNS service giao tiếp với nhau
- các DNS được liên kết với nhau


trường hợp không phân giải được IP, có thể đổi DNS provider 
1.1.1.1 là của cloudflare 
8.8.8.8 là của google 

### note on http 

[[Linux - stateful and stateless protocol]]
[[Linux - Session and sessionless communication]]
[HTTP là gì? HTTP khác HTTPS như thế nào?](https://vietnix.vn/http-la-gi/)
- stateless nhưng không sessionless 
- Trước khi một client và server thực hiện trao đổi một cặp Yêu cầu – Phản hồi HTTP, chúng sẽ phải thiết lập ra một kết nối **TCP**.
- HTTP 1.1, HTTP/2

https: có ssl can thiệp payload ở tầng 7, mã hóa nội dung của http. trái lại, http thường chỉ bao gồm các chuỗi bit chưa được mã hóa, có thể biến thành plain text. 

## ICMP 

[[Linux - ICMP]]

## OSI 

[[Linux - OSI model]]
[[Linux - package and frames]]

## other concepts 

routing table 
default pathway 
tcp handshake process 
osi packaging and framing process 
tcp header / ip header / http header
obsidian quartz the whole thing 


















