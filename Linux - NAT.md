---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 12
creation date: 2024-12-12 10:15
modification date: Thursday 12th December 2024 10:15:02
---

#computerScience/networking #linux #job/vietnix 
## Article link:
[Network Address Translation (NAT) - GeeksforGeeks](https://www.geeksforgeeks.org/network-address-translation-nat/)
[NAT là gì? Toàn tập kiến thức về NAT từ A đến Z](https://fptcloud.com/nat-la-gi/)
related notes: 
- [[]]
_____
## Overview 

**Dịch Địa Chỉ Mạng (NAT)** là một quá trình trong đó:
- một hoặc nhiều địa chỉ IP cục bộ được dịch thành một hoặc nhiều địa chỉ IP toàn cầu và ngược lại để cung cấp quyền truy cập Internet cho các máy chủ cục bộ. 
- thực hiện việc dịch số cổng, nghĩa là che giấu số cổng của máy chủ bằng một số cổng khác trong gói tin sẽ được định tuyến đến đích. Sau đó, nó tạo các mục tương ứng của địa chỉ IP và số cổng trong bảng NAT (nat table).
- NAT thường hoạt động trên một [bộ định tuyến hoặc tường lửa](https://www.geeksforgeeks.org/difference-between-router-and-firewall/).


![NAT là gì 2](https://fptcloud.com/wp-content/uploads/2022/03/Chuc-nang-chinh-cua-NAT-chuyen-doi-IP-noi-mien-thanh-IP-ngoai-mien.jpg "NAT là gì? Toàn tập kiến thức về NAT từ A đến Z 13")
## Phân loại nat 

### **Static NAT**

- biến đổi IP này thành IP khác thông qua cách cố định từ IP sang IP Public. 
- thực hiện hoàn toàn thủ công. 
- ứng dụng trong trường hợp thiết bị cần truy cập vào hệ thống từ bên ngoài.
![NAT là gì 5](https://fptcloud.com/wp-content/uploads/2022/03/Static-NAT-ky-thuat-bien-doi-IP-nay-thanh-IP-khac.jpg "NAT là gì? Toàn tập kiến thức về NAT từ A đến Z 17")


Static NAT là NAT dạng tĩnh, cho phép biến đổi IP Private thành IP Public. NAT tĩnh 

### **4.2 Dynamic NAT**

- chuyển đổi từ một địa chỉ IP sang kiểu IP khác hoàn toàn tự động. 
- biến đổi đổi ip mạng cục bộ thành IP đăng ký hợp lệ.

### **4.3 NAT Overload**

- là một kiểu giao thức của NAT động. Số lượng lớn địa chỉ IP có thể quy về một IP Public qua hệ thống cổng Port. 
- Mỗi Port thường chia thành các NAT ứng với các mức độ.

## nat table 

The NAT table is the heart of the whole NAT operation.

takes place within the router (or any NAT-enabled device) as packets arrive and leave its interfaces. 

Each connection from the internal (private) network to the external (public-Internet) network, and vice versa, is tracked and a special table is created to help the router determine what to do with all incoming packets on all of its interfaces 

![nat-table-2](https://www.firewall.cx/images/stories/nat-table-2.gif)

