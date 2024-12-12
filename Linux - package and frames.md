---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 12
creation date: 2024-12-12 12:27
modification date: Thursday 12th December 2024 12:27:27
---

#job/vietnix #linux 
## Article link:

[OSI Model: Packets vs. Frames | Baeldung on Computer Science](https://www.baeldung.com/cs/osi-packets-vs-frames)
[Encapsulation in OSI and TCP/IP Models - Study CCNA](https://study-ccna.com/encapsulation/)
_____
## comparision table 

| Frame                                     | Packet                               |
| ----------------------------------------- | ------------------------------------ |
| Data link layer data transmission unit    | Network layer data transmission unit |
| Associated to Layer 2                     | Associated to Layer 3                |
| Physical Addressing                       | Logical Addressing                   |
| Source and Destination MAC address        | Source and Destination IP address    |
| Data link layer header + Packet + Trailer | Network layer header + Segment       |
| Contains a trailer part                   | Doesn’t contain a trailer part       |
| Encapsulates a packet                     | Encapsulated within a frame          |

## Frame và Packet là gì?

**Frame** và **packet** là hai thuật ngữ thường gặp trong mạng máy tính, chúng đại diện cho các đơn vị dữ liệu được truyền đi qua mạng. Mặc dù có vẻ giống nhau, nhưng chúng hoạt động ở các tầng khác nhau trong mô hình OSI và có những đặc điểm riêng biệt.

### Frame (Khung)


![Ethernet](https://www.baeldung.com/wp-content/uploads/sites/4/2021/10/Ethernet.png)

- là một đơn vị dữ liệu được định dạng đặc biệt, được sử dụng để truyền dữ liệu qua mạng LAN (Local Area Network - mạng cục bộ).
- **Cấu trúc:** Một frame bao gồm các trường như:
    - **Địa chỉ MAC nguồn:** Địa chỉ vật lý của thiết bị gửi đi.
    - **Địa chỉ MAC đích:** Địa chỉ vật lý của thiết bị nhận.
    - **Dữ liệu:** Phần dữ liệu cần truyền đi.
    - **FCS (Frame Check Sequence):** Dùng để kiểm tra lỗi.
- **Tầng hoạt động:** Lớp liên kết dữ liệu (Data Link Layer).
- **Chức năng:**
    - **Định dạng dữ liệu:** Biến dữ liệu thành một cấu trúc có thể truyền đi được trên mạng LAN.
    - **Kiểm soát lỗi:** Phát hiện các lỗi xảy ra trong quá trình truyền.
    - **Điều khiển truy cập:** Quản lý việc truy cập vào môi trường truyền dẫn.


### Packet (Gói tin)

- là một đơn vị dữ liệu được định dạng đặc biệt, được sử dụng để truyền dữ liệu qua mạng IP (Internet Protocol).
- **Cấu trúc:** Một packet bao gồm các trường như:
    - **Địa chỉ IP nguồn:** Địa chỉ mạng logic của thiết bị gửi đi.
    - **Địa chỉ IP đích:** Địa chỉ mạng logic của thiết bị nhận.
    - **Dữ liệu:** Phần dữ liệu cần truyền đi.
    - **Các trường header khác:** Chứa thông tin về giao thức, phân mảnh, kiểm soát lỗi,...
- **Tầng hoạt động:** Lớp mạng (Network Layer).
- **Chức năng:**
    - **Định tuyến:** Định tuyến packet đến đích thông qua các mạng khác nhau.
    - **Phân mảnh:** Chia packet thành các phần nhỏ hơn nếu cần thiết.
    - **Tái hợp:** Ghép các phần nhỏ của packet lại thành packet ban đầu tại đích

![Datagram](https://www.baeldung.com/wp-content/uploads/sites/4/2021/10/datagram.png)