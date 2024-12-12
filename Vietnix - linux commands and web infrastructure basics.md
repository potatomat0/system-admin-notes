---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 10
creation date: 2024-12-10 15:49
modification date: Tuesday 10th December 2024 15:49:36
---

#job/vietnix #selflearn 
## Article link:

[[Vietnix - đào tạo]]
[DNS Lookup - Check All DNS Records for Any Domain](https://dnschecker.org/all-dns-records-of-domain.php)
[[Linux - SSl, TLS and HTTPS]]
[[Linux - What is DNS]]
_____

## protocols 

[[Linux - network protocols]]

## VNNIC

[Trung Tâm Internet Việt Nam (VNNIC)](https://vnnic.vn/)

**VNNIC** là cơ quan chính thức quản lý tên miền quốc gia ".vn" và địa chỉ IP của Việt Nam. Trang web của **VNNIC** cung cấp thông tin, tài nguyên, số liệu, hội nghị, chương trình và tin tức liên quan đến Internet Việt Nam.

## IANA 

[Internet Assigned Numbers Authority](https://www.iana.org/)
[Internet Assigned Numbers Authority - Wikipedia](https://en.wikipedia.org/wiki/Internet_Assigned_Numbers_Authority)

The global coordination of the DNS Root, IP addressing, and other Internet protocol resources is performed as the Internet Assigned Numbers Authority (IANA) functions.

## .htaccess

[[PHP - .htaccess]]

## ssh 

ssh default port: 22 
[[Linux - SSH connect]]
[[Linux - SSH Cheat Sheet]]
[OpenSSH Made Easy: The Ultimate Step-by-Step Tutorial - YouTube](https://www.youtube.com/watch?v=YS5Zh7KExvE&t=2740s)

basically you can't connect from one machine to another that uses wlan0, since that network is splitted to multiple users.

## DNS records and what they do 

[[Linux - all DNS records explained]]

## Cron jobs and back up 

[Schedule backup in Linux (rsync + cron) | Average Linux User](https://averagelinuxuser.com/automatically-backup-linux/)
[How to Set Up a Cron Job in Linux? {Schedule Tasks}](https://phoenixnap.com/kb/set-up-cron-job-linux)
[Rsync Command in Linux with Examples | Linuxize](https://linuxize.com/post/how-to-use-rsync-for-local-and-remote-data-transfer-and-synchronization/)
[[Linux - cron cheatsheet]]

```bash
# schedule rsync:  add the schedule of the rsync commands you want to run to the `crontab` file:

00 12 * * * rsync -aAX --delete --exclude '*.Trash-1000' /source/ /backup/daily
00 15 * * 5 rsync -aAX --delete --exclude '*.Trash-1000' /source/ /backup/weekly
00 16 1 * * rsync -aAX --delete --exclude '*.Trash-1000' /source/ /backup/monthly_$(date +%Y%m%d)
```

`our_backup_script.sh`

```
#! /bin/bash

DATE=$(date +%d-%m-%Y)
# Date in format DAY##-MONTH##-YEAR####

mkdir -p ~/archive/$DATE
# create a folder for today's date in the archive, if archive doesn't exist, make archive 
ls -al ~/Documents > ~/archive/$DATE/contents.txt
# create a text file listing the contents of the documents folder
cd ~/j  && tar -cpzf $DATE.docs.backup.gz Documents/*
# change to parent directory to tar /Documents folder
cp ~/$DATE.docs.backup.gz ~/archive/$DATE/documents_archive.gz
# one .gz file is left in the home directory, a clone is sent to our archive under it's date
```

## cpu and memory 

[[all CPU specs you should know - binarytides]]
[[How CPU works - cpu.land]]


## other concepts 

- Disk I/O 
- Cpanel's JetBackup - GUI backup, paid program 
- entry processes 
- IOPS (input/output pers second )
- cloudlinux - linux derivative for service providers 
- SSL ([[Linux - SSl, TLS and HTTPS]])
- imunify360 - paid anti virus service 
- SQL, mySQL, database, cPanel's integrated phpAdmin 
- lifespeed webserver, lscache 
- shell access 
- memcached socket and redis ([Redis Explained - by Mahdi Yusuf](https://architecturenotes.co/p/redis))
- DDoS, anti-DDoS firewall 

