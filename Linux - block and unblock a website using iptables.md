---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: September
day: 05
creation date: 2024-09-05 07:53
modification date: Thursday 5th September 2024 07:53:28
---

#internetContent  #linux 
## Article link:

related notes: 
- [[]]
_____
## Content

Blocking **sites** with iptables rules is a very bad idea, mainly because iptables (as most firewalls) deals with the IP addresses, and relationship between a site and its IP address(es) is rather loose:

1. One site can have _many_ IP addresses, which can be changed rather frequently. Once iptables rules are created, even if you specify a site's name as part of a rule, the first IP address _at that moment_ is used. If site's address changes, your iptables rules will be out of date.
    
2. One IP address can host many sites (and it happens often). This will only get more frequent, because of the IP address scarcity. If you block an IP address, you block all sites hosted on it.

>-A OUTPUT -p tcp -m string --string <domain_name> --algo kmp -j REJECT