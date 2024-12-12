---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 12
creation date: 2024-12-12 11:57
modification date: Thursday 12th December 2024 11:57:31
---

#linux #job/vietnix 
## Article link:
[What is OSI Model | 7 Layers Explained](https://www.geeksforgeeks.org/open-systems-interconnection-model-osi/)
[[Linux - package and frames]]
_____
## Content


![OSI-Model](https://media.geeksforgeeks.org/wp-content/uploads/20241111182857579134/OSI-Model.gif)


**có 7 tầng***


| Tên tầng                           | Chức năng chính                                                                                      | Các phương thức/giao thức tiêu biểu            |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| **Lớp ứng dụng/application**       | Cung cấp giao diện cho người dùng tương tác với các dịch vụ mạng.                                    | HTTP, FTP, SMTP, DNS, Telnet                   |
| **Lớp trình bày/presentation**     | **Mã hóa, nén, giải mã dữ liệu** để đảm bảo tính tương thích giữa các hệ thống khác nhau.            | ASCII, Unicode, JPEG, MPEG                     |
| **Lớp phiên/session**              | Quản lý các kết nối, đồng bộ hóa dữ liệu, kiểm soát luồng dữ liệu.                                   | RPC, NFS, SQL                                  |
| **Lớp vận chuyển/transport**       | Cung cấp dịch vụ truyền tin end-to-end, đảm bảo dữ liệu được truyền đi một cách tin cậy và hiệu quả. | TCP, UDP                                       |
| **Lớp mạng/network**               | Định tuyến gói tin giữa các mạng, **xác định địa chỉ IP**.                                           | IP, ICMP, ARP                                  |
| **Lớp liên kết dữ liệu/data link** | Truyền dữ liệu giữa các máy tính trong cùng một mạng, kiểm soát lỗi.                                 | Ethernet, PPP, Frame Relay                     |
| **Lớp vật lý/physical**            | Truyền tín hiệu bit trên môi trường vật lý.                                                          | Các chuẩn về cáp, tốc độ truyền, tín hiệu điện |
