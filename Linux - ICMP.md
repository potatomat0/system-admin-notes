---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 12
creation date: 2024-12-12 11:51
modification date: Thursday 12th December 2024 11:51:56
---

#job/vietnix #computerScience/networking 
## Article link:

related notes: 
- [[]]
_____


### ICMP 

[Hex Packet Decoder](https://hpd.gasmi.net/)
[Exploring ICMP with Examples - howtouselinux](https://www.howtouselinux.com/post/_icmp#ICMP_Packet_Structure)

**Lệnh và package liên quan:**
- ping - gửi ICMP ECHO_REQUEST tới network hosts
- iptables/ip6tables — công cụ quản trị IPv4/IPv6 packet filtering và [[Linux - NAT|NAT]]

**Common ICMP Types**

Type 0 — Echo reply

Type 3 — Destination unreachable

Type 8 — Echo

Type 5 — Redirect

**examle of ICMP**

*send an ICMP packet with ping command*

```bash
ping google.com (172.217.25.14): 56 data bytes

# ouptput: 64 bytes from 172.217.25.14: icmp_seq=0 ttl=111 time=49.412 ms
```

*Capture ICMP Packet with Tcpdump Command*

```bash
tcpdump -i utun1 -vvvv icmp -A -X -c 1 and dst google.com

# output:
45 00 00 54 89 82 00 00 40 01 BB 95 0A 4F 65 5B AC D9 19 0E 08 00 EC FC C9 50 00 00 60 2B 97 D8 00 08 5E A3 08 09 0A 0B 0C 0D 0E 0F 10 11 12 13 14 15 16 17 18 19 1A 1B 1C 1D 1E 1F 20 21 22 23 24 25 26 27 28 29 2A 2B 2C 2D 2E 2F 30 31 32 33 34 35 36 37
```

use [Hex Packet Decoder](https://hpd.gasmi.net/) to analyze the output 


![](http://sslhowto.files.wordpress.com/2021/07/5ac20-59b8e0_b202c4981fe344e39afc38af7d85e269mv2.png)

