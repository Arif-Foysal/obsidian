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

##### Mounting and Unmounting a Filesystem
###### Mounting
Making something accessible to the computer, like a filesystem or a hard disk.
##### Linux
To view what disks are connected to the computer-
`sudo parted -l`
o/p-
```
Model: ATA Lexar 256GB SSD (scsi)  
Disk /dev/sda: 256GB  
Sector size (logical/physical): 512B/512B  
Partition Table: gpt  
Disk Flags:    
  
Number  Start   End     Size    File system     Name  Flags  
2      9437kB  17.2GB  17.2GB  linux-swap(v1)        swap  
3      17.2GB  256GB   238GB   btrfs  
4      256GB   256GB   537MB   fat32                 boot, esp  
  
  
Model: INTEL SSDPEKNW512G8 (nvme)  
Disk /dev/nvme0n1: 512GB  
Sector size (logical/physical): 512B/512B  
Partition Table: gpt  
Disk Flags:    
  
Number  Start   End    Size   File system  Name  Flags  
1      1049kB  512GB  512GB  ext4
```

Here, The first column `Number` field corresponds to the partitions on the disk.
Since our disk `ATA Lexar 256GB SSD` is represented by `/dev/sda` , the partitions will correspond to according to the `Number` field-
`/dev/sda2` 
`/dev/sda3` and
`/dev/sda3`
The `Start` and `End` field is where the partitions starts on the disk.
The `Size` field represents how large the partition size is.
the `Filesystem` field tells us what filesystem is on our partition.

`Parted` is a interective CLI program that is used to format and partition disks in linux.
**Synopsis-**
`parted [options] [device [command [options...]...]]`
