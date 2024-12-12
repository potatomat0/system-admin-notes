---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: March
day: 17
creation date: 2024-03-17 22:10
modification date: Sunday 17th March 2024 22:10:46
---

#internetContent  #linux #computerScience/computerBasic 
## Article link:
[Fetching Title#sjgo](https://www.howtogeek.com/193669/whats-the-difference-between-gpt-and-mbr-when-partitioning-a-drive/)
related notes: 
- [[]]
_____
## Content

## KEY TAKEAWAYS

-  GPT is a newer partitioning standard that has fewer limitations than MBR, such as allowing for more partitions per drive and supporting larger drives.
-  Both Windows and macOS, as well as other operating systems, can use GPT for partitioning drives.
-  GPT is more robust and provides better data protection and recovery options compared to MBR, but MBR is still necessary for compatibility with older systems.

Set up a new disk on Windows 10 or Windows 11, and you'll be asked whether you want to use MBR (Master Boot Record) or GPT (GUID Partition Table). Today we're explaining the difference between GPT and MBR and helping you choose the right one for your PC or Mac.

GPT brings with it many advantages, but MBR is still the most compatible and is still necessary in some cases. This isn't a Windows-only standard, by the way — macOS, Linux, and other operating systems can also use GPT.

## What is a Partition?

A partition just refers to how the space on any kind of storage device — like hard drives, solid state drives, and flash drives — is divided up. Most of the time you only have one partition per drive, but there are plenty of times and cases where you'll have more than that. Take our "Disk 0," for example.

![Disk 0 has multiple partitions on it.](https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2023/08/drive-with-multiple-partitions.png)

A [partition](https://www.howtogeek.com/184659/beginner-geek-hard-disk-partitions-explained/) _structure_ defines how information is structured on the partition, where partitions begin and end, and also the code that is used during startup if a partition is bootable. If you've ever partitioned and formatted a disk — or [set up a Mac to dual boot Windows](https://www.howtogeek.com/186907/how-to-install-windows-on-a-mac-with-boot-camp/) — you've likely had to deal with MBR and GPT. GPT is the new standard and is gradually replacing MBR.

## What Do GPT and MBR Do?

[You have to partition a disk drive before you can use it](https://www.howtogeek.com/184659/beginner-geek-hard-disk-partitions-explained/). MBR (Master Boot Record) and GPT (GUID Partition Table) are two different ways of storing the partitioning information on a drive. This information includes where partitions begin and end on the physical disk, so your operating system knows which sectors belong to each partition and which partition is bootable. This is why you have to choose MBR or GPT before creating partitions on a drive.

![Initialize a disk on Windows 10](https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2023/08/initialize-disk.png)

MBR's Limitations MBR was first introduced with IBM PC DOS 2.0 in 1983. It's called Master Boot Record because the MBR is a special boot sector located at the beginning of a drive. This sector contains a boot loader for the installed operating system and information about the drive's logical partitions. The boot loader is a small bit of code that generally loads the larger boot loader from another partition on a drive. If you have Windows installed, the initial bits of [the Windows boot loader](https://www.howtogeek.com/192772/what-is-the-system-reserved-partition-and-can-you-delete-it/) reside here — that's why you may have to [repair your MBR](https://www.howtogeek.com/32523/how-to-manually-repair-windows-7-boot-loader-problems/) if it's overwritten and Windows won't start. If you have Linux installed, [the GRUB boot loader](https://www.howtogeek.com/114884/how-to-repair-grub2-when-ubuntu-wont-boot/) will typically be located in the MBR.

MBR does have its limitations. For starters, MBR only works with disks up to 2 TB in size. MBR also only supports up to four primary partitions — if you want more, you have to make one of your primary partitions an "extended partition" and create logical partitions inside it. This is a silly little hack and shouldn't be necessary.

## ![MBR is limited to four proper partitions.](https://static0.howtogeekimages.com/wordpress/wp-content/uploads/2023/08/mbr-limits.png)GPT's Advantages

GPT stands for GUID Partition Table. It's a new standard that's gradually replacing MBR. It's associated with UEFI, which [replaces the clunky old BIOS with something more modern](https://www.howtogeek.com/56958/htg-explains-how-uefi-will-replace-the-bios/). GPT, in turn, replaces the clunky old MBR partitioning system with something more modern. It's called GUID Partition Table because every partition on your drive has a "globally unique identifier," or GUID — a random string so long that every GPT partition on earth likely has its own unique identifier.

GPT doesn't suffer from MBR's limits. GPT-based drives can be much larger, with size limits dependent on the operating system and its [file systems](https://www.howtogeek.com/235596/whats-the-difference-between-fat32-exfat-and-ntfs/). GPT also allows for a nearly unlimited number of partitions. Again, the limit here will be your operating system — Windows allows up to 128 partitions on a GPT drive, and you don't have to create an extended partition to make them work.

On an MBR disk, the partitioning and boot data is stored in one place. If this data is overwritten or corrupted, you're in trouble. In contrast, GPT stores multiple copies of this data across the disk, so it's much more robust and can recover if the data is corrupted.

GPT also stores cyclic redundancy check (CRC) values to check that its data is intact. If the data is corrupted, GPT can notice the problem and attempt to recover the damaged data from another location on the disk. MBR had no way of knowing if its data was corrupted — you'd only see there was a problem when the boot process failed or your drive's partitions vanished.

![You can have a large amount of partitions on a GPT drive.](https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2023/08/gpt-partitions-for-days.png)

## Compatibility

GPT drives tend to include a "protective MBR." This type of MBR says that the GPT drive has a single partition that extends across the entire drive. If you try to manage a GPT disk with an old tool that can only read MBRs, it will see a single partition that extends across the entire drive. This protective MBR ensures the old tools won't mistake the GPT drive for an unpartitioned drive and overwrite its GPT data with a new MBR. In other words, the protective MBR protects the GPT data from being overwritten.

Windows can only boot from GPT on UEFI-based computers running 64-bit versions of Windows 11, 10, 8, 7, Vista, and corresponding server versions. All versions of Windows — 11, 10, 8, 7, and Vista — can read GPT drives and use them for data — they just can't boot from them without UEFI.

Other modern operating systems can also use GPT. Linux has built-in support for GPT. Apple's Intel Macs no longer use Apple's APT (Apple Partition Table) scheme and use GPT instead.

![Ubuntu, and other Linux distros, support GPT as well.](https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2017/02/gparted.png)

---

You'll probably want to use GPT when setting up a drive. It's a more modern, robust standard that all computers are moving toward. If you need compatibility with old systems — for example, the ability to boot Windows off a drive on a computer with a traditional BIOS — you'll have to stick with MBR for now.