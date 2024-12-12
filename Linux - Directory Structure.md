---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: February
day: 08
creation date: 2024-02-08 23:05
modification date: Thursday 8th February 2024 23:05:26
---

#internetContent  #linux 
## Article link:
[Linux Directory Structure - GeeksforGeeks](https://www.geeksforgeeks.org/linux-directory-structure/)
related notes: 
- [[Linux - Bios vs Kernel]]
_____
## Content

- **`/bin`:** **Essential user binaries** for basic operations (ls, cp, cat).
- **`/sbin`:** **Essential system administration binaries** (not for normal users).
- **`/lib`:** **Shared libraries** used by programs (not executables).
- **`/usr`:** **User-related programs and data:**
    - `/usr/bin`: **More user programs** than `/bin`.
    - `/usr/lib`: **Shared libraries** for user programs.
    - `/usr/share`: **Shared data** like fonts and icons.
- **`/etc`:** **System configuration files**:
    - `/etc/passwd`: User accounts information.
    - `/etc/shadow`: Encrypted user passwords.
    - `/etc/hosts`: Local hostname mappings.
    - `/etc/fstab`: Filesystem mount information.
- **`/home`:** **User home directories** for personal data.
- **`/boot`:** **Bootloader files** and kernel image.
- **`/dev`:** **Device files** representing hardware (e.g., /dev/sda for hard drive).
- **`/tmp`:** **Temporary files** (automatically deleted at reboot).
- **`/var`:** **Variable data files** that change often (logs, caches).

**Bonus Folders:**

- **`/opt`:** **Optional software** installed by the user.
- **`/mnt`:** **Mount point** for temporary filesystems.
- **`/proc`:** **Process information** (not actual files).
- **`/sys`:** **System information** (not actual files).

