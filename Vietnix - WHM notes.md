---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 11
creation date: 2024-12-11 10:09
modification date: Wednesday 11th December 2024 10:09:37
---

## WHM commands 
#job/vietnix #WHM 
[WHM | cPanel & WHM Documentation](https://docs.cpanel.net/whm/)

### reload user 

> cagefs -m

### check domlogs 

```bash
#domain không có ssl: 

/var/log/apache2/domlogs/<domain>

#domain có ssl 

/var/log/apache2/domlogs/<domain>-ssl_log 
```

### check process đang chạy của một user 

>ps | grep `<user>`

### tìm một add-on domain đang thuốc user nào 

search: list account
-> list subdomains 
-> fill in the form with the domain 

```bash
cat /ect/userdatadomains | grep "conheo.com"

abc.conheo.com:
```

###  kiểm tra hosting đang kết nối mail relay server bằng port nào 

search: exim.com 
-> advanced editor 
-> section: POSTMAILCOUNT 
-> port nằm ở 'route_list =...'

### PHP X-ray


dùng để trace cụ thể thời gian thực thi các function php, giúp phát hiện các function nào gây chậm website của khách hàng 

-> search cloudlinux 
-> click on start tracing 
-> type in the URL (domain), fill the client's IP (usually just the \*). on the `record for`: `time period` is tracing within a duration of time. `request` is the amount of request

-> click on the eye icon under the actions column 

### đổi primary domain 

search: modify an accoutn 
-> find user -> modify -> under the primary domain form, change the value -> save 

### migrate and transer 

find: transfer 

in transfer tool -> fill the IP address of the current server in the `remote server address`
-> authentication method: SSH public key; SSH key: transfer
--> scane the remote server, find the user that needs the transfer -> copy 