---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 11
creation date: 2024-12-11 10:20
modification date: Wednesday 11th December 2024 10:20:08
---

#linux #selflearn 
## Article link:

[What is RAID? RAID 0, 1, 5, & 10 Made Easy - The Plug - HelloTech](https://www.hellotech.com/blog/what-is-raid-0-1-5-10)
_____
## What Is RAID 0?

![461px-Raid0](https://www.hellotech.com/blog/wp-content/uploads/2020/01/461px-Raid0.jpg)

Also called “disk striping,” RAID 0 is all about optimizing the speed of your hard drives. If you have at least two drives, using RAID 0 will combine them and write data on both of them simultaneously or sequentially, depending on your system. This will help with read and write speeds. However, if one drive fails, you will lose all of your data.

When you save a file, RAID 0 breaks the data into segments called striped units. Then it spreads that data across all of the drives in your array. This is called striping, and it helps you access data faster because you have multiple drives working together to read, write, and store data.

Using RAID 0 is faster than getting a large hard drive with the same capacity because you would only have one hard drive processing data instead of multiple drives in an array.

However, RAID 0 does not include any redundancy (or backups). That means if one of your drives fails, you lose all the data on that drive. And, since your data is stored and processed across multiple drives, losing the data on one drive means you lose all of the data on all of your drives. Plus, since you are using multiple disks, the chance that one of them will fail is increased.

RAID 0 is best used for storing temporary files or files that you have backed up elsewhere.

## What is RAID 1?

![RAID 1 231x300](https://www.hellotech.com/blog/wp-content/uploads/2020/01/RAID-1-231x300.png)

Otherwise known as “disk mirroring,” RAID 1 is all about backing up data (also known as redundancy). If you have at least two drives, using RAID 1 will duplicate your data and store a copy on each drive. This is called mirroring, and it ensures you won’t lose your files if a drive fails.

Using RAID 1 means that if one drive fails, you’ll still have a copy of all your data on the other drive. Then, you can replace the failed drive with a new one, even while the computer is still running. It will automatically create a new mirror image of all your data on the good drive. This capability in RAID arrays is called hot-swappable.

However, using RAID 1 means that you will only get half the storage capacity that you would get otherwise. This is because every time you save a file to one drive, you save a copy to a second drive.

RAID 1 is best used for storing data that you don’t want to lose, such as crucial banking data or family photos and documents.

## What is RAID 5?

![what is RAID 5](https://www.hellotech.com/blog/wp-content/uploads/2020/01/RAID-5.png)

Also known as “disk striping with parity,” RAID 5 is about speed and redundancy. If you have at least three hard drives, using RAID 5 will break your data into segments and save those segments across your drives.

Now, when you write data in this array, just like in RAID 0, your data is broken down into units and spread over the hard drives in your array. But, aside from striping the data, it also stores parity bits on the drives. A parity bit is an additional binary digit that helps your array check if there’s any error or missing segments. These bits of data can also serve as redundancies.

Just like with Disk Mirroring, the drives in this array are also hot-swappable. So if one drive fails, you can easily replace it with a new one, and the array will automatically recreate your RAID configuration.

However, RAID 5 will not offer you the same speed as RAID 1 or the same capacity as RAID 0. It will take processing power to create the parity bits, and some storage space will be set aside for the redundancies. So, if you have three hard drives with 500GB of storage each, you will only get 1TB worth of capacity because one-third of the space will be allocated for redundancies.

This setup is best for storing critical data and running applications that need decent speed and efficiency.

## What is RAID 10?

![what is RAID 10](https://www.hellotech.com/blog/wp-content/uploads/2020/01/RAID-10.png)

Classified as a “hybrid RAID configuration,” RAID 10 is actually a combination of RAID 1+0. This means you get the speed of disk striping and the redundancies of disk mirroring. For techies, this is also called a “stripe of mirrors.”

If you have at least four drives, RAID 10 will increase the speed that you would have with just one drive, and you get the advantages of having redundancies. However, this also means that you have to buy more drives, and you only get half the capacity of all of them.

RAID 10 is best for running applications or hosting servers that need to be up 24/7. If one or two of your drives fail, you still have the mirror drive with all your data intact in them.