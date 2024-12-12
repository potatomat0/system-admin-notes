---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 12
creation date: 2024-12-12 09:25
modification date: Thursday 12th December 2024 09:25:16
---

#computerScience/networking #linux 
## Article link:
[[Linux - Session and sessionless communication]]
related notes: 
- [[]]
_____
## Content

| Stateless Protocol                                                                                                                                                                                                                           | Stateful Protocol                                                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Stateless Protocol does not require the server to retain the server information or session details.                                                                                                                                          | Stateful Protocol require server to save the status and session information.                                                                                               |
| In Stateless Protocol, there is no tight dependency between [server](https://www.geeksforgeeks.org/introduction-of-server/) and [client](https://www.geeksforgeeks.org/client-server-model/).                                                | In Stateful protocol, there is tight dependency between server and client                                                                                                  |
| The Stateless protocol design simplify the server design.                                                                                                                                                                                    | The Stateful protocol design makes the design of server very complex and heavy.                                                                                            |
| Stateless Protocols works better at the time of crash because there is no state that must be restored, a failed server can simply restart after a crash.                                                                                     | Stateful Protocol does not work better at the time of crash because stateful server have to keep the information of the status and session details of the internal states. |
| Stateless Protocols handle the transaction very quickly.                                                                                                                                                                                     | Stateful Protocols handle the transaction very slowly.                                                                                                                     |
| Stateless Protocols are easy to implement in Internet.                                                                                                                                                                                       | Stateful protocols are logically heavy to implement in Internet.                                                                                                           |
| Scaling architecture is relatively easier.                                                                                                                                                                                                   | It is difficult and complex to scale architecture.                                                                                                                         |
| The requests are not dependent on the server side and are self contained.                                                                                                                                                                    | The requests are always dependent on the server side.                                                                                                                      |
| To process different information at a time , different servers can be used.                                                                                                                                                                  | To process every request , the same server must be utilized.                                                                                                               |
| Example of Stateless are [UDP](https://www.geeksforgeeks.org/user-datagram-protocol-udp/) , [DNS](https://www.geeksforgeeks.org/domain-name-system-dns-in-application-layer/) , [HTTP](https://www.geeksforgeeks.org/http-full-form/) , etc. | Example of Stateful are [FTP](https://www.geeksforgeeks.org/file-transfer-protocol-ftp/) , [Telnet](https://www.geeksforgeeks.org/introduction-to-telnet/) , etc.          |

| Tiêu chí so sánh     | Stateless                                                                                               | Stateful                                                                                      |
| -------------------- | ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Khái niệm và ví dụ   | Stateless là trạng thái không lưu toàn bộ thông tin về Client trong Server.  <br>Ví dụ: UDP, HTTP, DNS. | Stateful là trạng thái có lưu trữ thông tin của Client trong Server.  <br>Ví dụ: Telnet, FTP. |
| Điểm yếu của máy chủ | Các thông tin máy chủ hay dữ liệu chi tiết mỗi phiên của nó đều không được lưu trữ.                     | Để duy trì trạng thái ở thời điểm cụ thể và dữ liệu phiên thì máy chủ được lưu giữ thông tin. |
| Sự phụ thuộc         | Mối liên kết giữa máy chủ và máy khách không bị ràng buộc. Cả hai bên đều được phép hoạt động độc lập.  | Mối liên kết giữa máy chủ và máy khách bị ràng buộc (không thể hoạt động độc lập).            |
| Thiết kế             | Máy chủ được thiết kế khá đơn giản.                                                                     | Máy chủ được thiết kế rất phức tạp dẫn đến việc khó thực hiện nhiều hoạt động.                |
| Sự cố                | Trường hợp xảy ra sự cố, máy chủ sẽ khởi động lại một cách dễ dàng.                                     | Do đặc thù lưu trữ nhiều dữ liệu riêng biệt, thế nên khi xảy ra sự cố rất khó quản lý.        |
| Tốc độ               | Các giao dịch sẽ được máy chủ xử lý vô cùng nhanh chóng.                                                | Tốc độ xử lý giao dịch khá chậm.                                                              |