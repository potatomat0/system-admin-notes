---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: January
day: 04
creation date: 2024-01-04 17:22
modification date: Thursday 4th January 2024 17:22:26
---

#internetContent  #linux 
## Article link:
[Error: Network Manager is not running : r/archlinux](https://www.reddit.com/r/archlinux/comments/r8qwe8/error_network_manager_is_not_running/)
[NetworkManager - ArchWiki](https://wiki.archlinux.org/title/NetworkManager#Usage)
related notes: 
- [[tech support - debian 12 no connections available]]
_____
## Content

If you are wired connected to the internet try this for wifi and ethernet :

In gnome/GTK scenario:

`sudo pacman -S iw dialog wpa_supplicant networkmanager network-manager-applet`

In Plasma/QT scenario:

`sudo pacman -S iw dialog wpa_supplicant networkmanager plasma-nm networkmanager-qt`

Then run:

`sudo systemctl enable NetworkManager.service`

`sudo systemctl start NetworkManager.service`

`sudo systemctl enable wpa_supplicant.service`

`sudo systemctl start wpa_supplicant.service`

Then run nmtui to configure wired and wireless interfaces:

`sudo nmtui`

