---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 11
creation date: 2024-12-11 10:17
modification date: Wednesday 11th December 2024 10:17:01
---

#linux #job/vietnix #selflearn 
## Article link:

[What are DNS records? | Cloudflare](https://www.cloudflare.com/learning/dns/dns-records/)

related notes: 
- [[Linux - What is DNS]]
_____

DNS records  

[DNS Lookup - Check All DNS Records for Any Domain](https://dnschecker.org/all-dns-records-of-domain.php)

A, AAAA, CNAME, NS, MX, PTR, SRV, SOA, TXT, CAA, DS, DNSKEY

### A record 

The "A" stands for "address" and this is the most fundamental type of [DNS](https://www.cloudflare.com/learning/dns/what-is-dns/) record: it indicates the [IP address](https://www.cloudflare.com/learning/dns/glossary/what-is-my-ip-address/) of a given [domain](https://www.cloudflare.com/learning/dns/glossary/what-is-a-domain-name/).

usually used for matching a domain name (like "cloudflare.com") to an IPv4 address

**example**:

| example.com | record type: | value:    | TTL   |
| ----------- | ------------ | --------- | ----- |
| @           | A            | 192.0.2.1 | 14400 |
- @: the root domain 
- 192.0.2.1: ipv4 IP address 
- 144400: TTL (time to live). if A record gets update, it tals 14400 milisecond to be effected 

The vast majority of websites only have one A record, but it is possible to have several.

### AAAA 

The DNS AAAA record **matches a domain name with an IPv6 address** — similar to A records, which do the same for IPv4 addresses.

- IPv6 is the latest version of the [Internet Protocol (IP)](https://www.cloudflare.com/learning/network-layer/internet-protocol/)
- the world is running out of IPv4
- IPv6 addresses are longer than IPv4 addresses. 

| example.com | record type: | value:                                        | TTL   |
| ----------- | ------------ | --------------------------------------------- | ----- |
| @           | AAAA         | 2001:0db8:85a3:0000:  <br>0000:8a2e:0370:7334 | 14400 |

- AAAA records enable client devices to learn the IP address for a domain name. The client device can then connect with and load the website.
- only used when a domain has an IPv6 address in addition to an IPv4 address
- not all domains have IPv6 addresses

### CNAME 

The DNS CNAME (canonical name) record **works as an alias for domain names** that share a single IP address.

Example: 

- blog.example.com has a CNAME record with a value of "example.com"
- when a [DNS](https://www.cloudflare.com/learning/dns/what-is-dns/) server hits the [DNS records](https://www.cloudflare.com/learning/dns/dns-records/) for `blog.example.com`, it actually triggers **another DNS lookup** to example.com, returning example.com’s IP address via its A record
- when sites have subdomains such as `blog.example.com` or `shop.example.com`, those subdomains will have CNAME records that point to a root domain (`example.com`)

| blog.example.com | record type: | value:                     | TTL   |
| ---------------- | ------------ | -------------------------- | ----- |
| @                | CNAME        | is an alias of example.com | 32600 |
| criticaoptica    | CNAME        | potatomat0.github.io       | 14400 |
| resume           | CNAME        | potatomat0.github.io       | 14400 |

MX and NS records cannot point to a CNAME record; they have to point to an A record (for IPv4) or an [AAAA record](https://www.cloudflare.com/learning/dns/dns-records/dns-aaaa-record/) (for IPv6).

### MX 

- The MX (mail exchange) record directs emails to a mail exchange server.
- MX record indicates how [email](https://www.cloudflare.com/learning/email-security/what-is-email/) messages should be routed in accordance with the Simple Mail Transfer Protocol ([SMTP](https://www.cloudflare.com/learning/email-security/what-is-smtp/), the standard protocol for all email).

example:

| example.com | record type: | priority: | value:                | TTL   |
| ----------- | ------------ | --------- | --------------------- | ----- |
| @           | MX           | 10        | mailhost1.example.com | 45000 |
| @           | MX           | 20        | mailhost2.example.com | 45000 |

- the priority is the preference. the lower it is, the more it is prioritized
- The server will always try mailhost1 first because 10 is lower than 20. 
- In the result of a message send failure, the server will default to mailhost2.
	- if `mailhost1` and `mailhost2` both has priority = 10, they both recieve the same amount of mail 

### TXT 

- The TXT record lets a domain admin leave notes on a DNS server.
- stored in the form of one or more strings within quotation marks.
- usually human-readable text 
- it is used for: 
	- email spam prevention 
	- ownership verification 

Example: 

| example.com | record type: | value:                                              | TTL   |
| ----------- | ------------ | --------------------------------------------------- | ----- |
| @           | TXT          | "This is an awesome domain! Definitely not spammy." | 32600 |
| @           | TXT          | "printer=lpr5"                                      | 32600 |
| @           | TXT          | "favorite drink=orange juice"                       | 32600 |

### NS 

- The NS (nameserver) record indicates which DNS server is authoritative.
- tell the Internet where to go to find out a domain's [IP address](https://www.cloudflare.com/learning/dns/glossary/what-is-my-ip-address/)
- Without properly configured NS records, users will be unable to load a website or application.

| example.com | record type: | value:                | TTL   |
| ----------- | ------------ | --------------------- | ----- |
| @           | NS           | ns1.exampleserver.com | 21600 |
 NS records **can never point to a CNAME record**

```bash
# usse linux command to lookup
nslookup 
```

### less commonly used DNS record 

- **AFSDB record** - This record is used for clients of the Andrew File System (AFS) developed by Carnegie Melon. The AFSDB record functions to find other AFS cells.
- **APL record** - The ‘address prefix list’ is an experiment record that specifies lists of address ranges.
- **CAA record** - This is the ‘certification authority authorization’ record, it allows domain owners state which certificate authorities can issue certificates for that domain. If no CAA record exists, then anyone can issue a certificate for the domain. These records are also inherited by subdomains.
- **DNSKEY record** - The ‘[DNS Key Record](https://www.cloudflare.com/learning/dns/dns-records/dnskey-ds-records/)’ contains a [public key](https://www.cloudflare.com/learning/ssl/how-does-public-key-encryption-work/) used to verify [Domain Name System Security Extension (DNSSEC)](https://www.cloudflare.com/learning/dns/dns-security/) signatures.
- **CDNSKEY record** - This is a child copy of the DNSKEY record, meant to be transferred to a parent.
- **CERT record** - The ‘certificate record’ stores public key certificates.
- **DCHID record** - The ‘DHCP Identifier’ stores info for the Dynamic Host Configuration Protocol (DHCP), a standardized network protocol used on IP networks.
- **DNAME record** - The ‘delegation name’ record creates a domain alias, just like CNAME, but this alias will redirect all subdomains as well. For instance if the owner of ‘example.com’ bought the domain ‘website.net’ and gave it a DNAME record that points to ‘example.com’, then that pointer would also extend to ‘blog.website.net’ and any other subdomains.
- **HIP record** - This record uses ‘Host identity protocol’, a way to separate the roles of an IP address; this record is used most often in mobile computing.
- **IPSECKEY record** - The ‘IPSEC key’ record works with the [Internet Protocol Security (IPSEC)](https://www.cloudflare.com/learning/network-layer/what-is-ipsec/), an end-to-end security protocol framework and part of the Internet Protocol Suite [(TCP/IP)](https://www.cloudflare.com/learning/ddos/glossary/tcp-ip/).
- **LOC record** - The ‘location’ record contains geographical information for a domain in the form of longitude and latitude coordinates.
- **NAPTR record** - The ‘name authority pointer’ record can be combined with an [SRV record](https://www.cloudflare.com/learning/dns/dns-records/dns-srv-record/) to dynamically create URI’s to point to based on a regular expression.
- **NSEC record** - The ‘next secure record’ is part of DNSSEC, and it’s used to prove that a requested DNS resource record does not exist.
- **RRSIG record** - The ‘resource record signature’ is a record to store digital signatures used to authenticate records in accordance with DNSSEC.
- **RP record** - This is the ‘responsible person’ record and it stores the email address of the person responsible for the domain.
- **SSHFP record** - This record stores the ‘SSH public key fingerprints’; SSH stands for Secure Shell and it’s a cryptographic networking protocol for secure communication over an unsecure network.

