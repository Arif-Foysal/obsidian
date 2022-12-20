#### Disk Partitioning
Partitions act as own seperate sub disks. 
When you formate a file system in a partition, it becomes a **Volume**
##### Partition Table
A partition table tells the operating system how the disk is partitioned. This includes which partitions you can boot from, how much space is allocated etc.
There are two main partition table is used-
	- MBR (Master Boot Record)
	- GPT (GUID Partition Table)

> **MBR Partition Table**
> - Traditional Partition Table
> - Mostly Used in windows
> - 2TB max volume size
> - It also uses primary partitions
> - It can only have 4 primary partitions in the disk
> - If you want to add more, you can take one primary partition, and make a extended partition. Inside the extended partition, you can make Logical Partition.

>**GPT Partition Table**
>- Supports 2TB or greater volume size.
>- One type of partition
>- Can have Unlimited Partition
>- UEFI is a BIOS standard that is default BIOS for newer systems. To use UEFI, the disk has to use GPT Partition Table.

#### Disk Partitioning and Formatting Filesystem
##### Windows
**Disk Management Utility** is a tool in windows that can be used to partition and format filesystems.
To access Disk management-
	computer management > storage > disk management
**Disk Manipulation from CLI**
**Diskpart** is a CLI tool that can be used in this purpose. 

Initialize Diskpart-
`Diskpart`

List the disks on the system-
`list disk`

stdout-
```
  Disk ###  Status         Size     Free     Dyn  Gpt
  --------  -------------  -------  -------  ---  ---
  Disk 0    Online          931 GB  1024 KB
  Disk 1    Online          238 GB  1024 KB        *
```

Now we can select a disk for further operations-
`select disk 1`
We can wipe the disk (removing all partition or volume from the disk) using-
`clean`
Create a blank partition on the filesystem-
`create partition primary`

Select the freshly created partition-
`select partition 1`
Mark the partition active-
`active`

Now we can format the disk with any file system-
`format FS=NTFS label=my-drive quick`

Supplemental Reading-
[[Diskpart]]
