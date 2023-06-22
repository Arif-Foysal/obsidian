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
`Parted` is a interective CLI program that is used to format and partition disks in linux.
**Synopsis-**
`parted [options] [device [command [options...]...]]`

List partition layouts of connected block devices-
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

##### partitioning a disk
We can partition a disk by running the interective mode of `parted`-
`sudo parted /dev/sdb`
o/p-
```
GNU Parted 3.4  
Using /dev/sdb  
Welcome to GNU Parted! Type 'help' to view a list of commands.  
(parted) print                                                               
Model: JetFlash Transcend 32GB (scsi)  
Disk /dev/sdb: 30.6GB  
Sector size (logical/physical): 512B/512B  
Partition Table: loop  
Disk Flags:    
  
Number  Start  End     Size    File system  Flags  
1      0.00B  30.6GB  30.6GB  fat32  
  
(parted)
```

Create a new disklabel (partition table) -
`mklabel gpt`

Make a partition-
**Synopsis**
`mkpart PART-TYPE [FS-TYPE] START END`
**E.g.**
`mkpart primary ext4 1MiB 5GiB`
Learn about [[partition types]]

Format the partition-
`sudo mkfs ext4 /dev/sdb1`

#### Mounting and unmounting Filesystems

Mount a filesystem-
`sudo mount <device> <path to mount>`

Unmount a filesystem-
`sudo umount <device>`

File systems can be mounted on startup using [[fstab]]
To do this, we need to modify a file located in `/etc/fstab`

Each devices has a **UUID** (Universally Unique ID).  To view **UUIDs** of connected block devices-
`sudo blkid`
[[swap memory]]
#### Swap Memory
swap memory is _the dedicated amount of hard drive that is used whenever RAM runs out of memory_.
##### Windows
Windows os uses a program called **Memory Manager** to handle virtual memory. It's job is to take care of the mapping of virtual to physical memory for our programs and to manage paging.
In windows, pages saved to disk are stored in a special hidden file on the root partition of a volume called ==pagefile.sys==.
Windows automatically created the page files and uses  memory manager to copy pages of memory to be read as needed. The OS does a pretty good job managing the page file automatically. Even so, windows provides a way to modify the size, number and location of pagefiles through a control panel applet called ==system properties==.
To access ==system properties== -
```
control panel > system and security > system > advanced system setting > adcanced > performance(settings) > advanced
```
You should see a section called virtual memory which displays the paging file size.
You can change the paging file size from here.
Lean more- [[Windows Paging Files]]


##### Linux
In linux, the dedicated area of the hard drive is used for virtual memory, known as **swap space**.
**Creating a swap partition-**
- Use `parted` followed by the disk
`sudo parted /dev/sdb`
- set up a swap area using `mkswap`-
`sudo mkswap /dev/sdb2`
- Enable swapping on that partition-
`sudo swapon /dev/sdb2`

#### The windows filesystem(NTFS)-
NTFS uses [[MFT(Master File Table)]].
Every file in volume has at least one entry in the MFT. This includes-
	- File name
	- Timestamp
	- Permissions
	- Location
etc.

When you create a file in the NTFS file system, entries get added to the MFT. When files get deleted,  their entries in MFT is marked as free.

==shortcut== is a special type of file in windows. It has a reference to some destination, so when you open the file, you are taken to that destination.
To create shortcut, right click on the file and click create shortcut.

NTFS has 2 other ways to link file-
	- [[Hard Links]]
	- [[Symbolic Links]]
**Symbolic Links** are kind of like shortcuts, but file system level. When you create a symbolic link, you basically create an entry in MFT that points another entry or another file. 

When you try to read the contents of a shortcut-
`cat file.shortcut`
It returns a random string that is not readable by us.

We can overcome this problem by creating symbolic link or hard link.
To create a symbolic link-
`mklink <outFile> <inFile>`

symbolic links are not accessable when the name of the file is changes

When you create a hard link, an entry is added to the MFT that points to the linked file record number. So the file name of the target can change, and hard links can still point to it. Which does not happen in symbolic links.
Craeting hard link-
`mklink /H <outFile> <inFile>`
``
#### Linux Filesystem

In linux, metadata and files are organized into a structure called [[inode]].
Inodes are similar to MFT records of windows. Inode itself doesnot contain the filename and the file data itself, but it contains everything else about the file. 
Shortcuts in linux are reffeerd to as softlinks or symlinks. They work in a similar way symbolic link work in windows. They basically point to another file. 
Hardlinks in linux do not point to a file. They link to an inode which is stored in an inode table on the filesystem. When you create a hardlink, you point to a physical location on a disk. If you delete a file of a hardlink, all other hardlinks would still work.

if you list contents using `ls -l`
o/p-
```
-rw-rw-r-- 1 mrx mrx 1474873344 Oct 19 22:50  ubuntu-22.04.1-live-server-amd64.iso
```
the number (1) after the permissions indicates the amount of hardlinks a file has.
when the hardlink count of a file is `0`, this means the file is completely removed from the computer. 
##### Creating Symlinks in Linux
`ln` command can be used to create symlinks in linux.

To create a softlink-
```
ln -s <source-location> <symlink-location>
```
To create a hardlink, we run the same command without the flag `-s`-

`ln <source-location> <symlink-location>`


#### Disk Usage
##### Windows
To check disk usage,

you can open up the computer management utility.

Then head to the `disk management console`.
From there, right click on the partition you're interested in and select properties.

Windows also provides a command line utility called `Disk usage` that can be used for for the same purpose.
###### Disk Usage using Command line
Du (disk usage) reports the disk space usage for the directory you specify. By default it recurses directories to show the total size of a directory and its subdirectories.

## Using Disk Usage (DU)

**Usage: du [-c[t]] [-l <levels> | -n | -v] [-u] [-q] <directory>**

|Parameter| Description |
|---------|-------------|
|**-c**|Print output as CSV. Use -ct for tab delimiting.|
| **-l** | Specify subdirectory depth of information (default is 0 levels). |
| **-n** | Do not recurse. |
| **-v** | Show size (in KB) of intermediate directories. |
| **-u**  | Count each instance of a hardlinked file. |
| **-q** | Quiet. |
| **-nobanner** | Do not display the startup banner and copyright message. |

CSV output is formatted as:

Path, CurrentFileCount, CurrentFileSize, FileCount, DirectoryCount, DirectorySize, DirectorySizeOnDisk

In the properties window, the `Disk Cleanup` button does some cleanup to the system. This includes deleting temporary files, compressing old and rarely used files etc. 
[[Defragmentation]] is the idea to take all the files stored on a given disk, and rorganize them into neighbouring locations. SSD's usually do not need defragmentation. [[Defragmentation]] in windows is handled as a scheduled task. 
###### Disk cleanup using command line
To start the Disk Cleanup tool and specify the hard disk to be cleaned by using the command line, follow these steps:  

1.  Click **Start**, and then click **Run**.
    
2.  In the **Open** box, type the following command, and then press Enter:
    
    ```c:\windows\SYSTEM32\cleanmgr.exe /d**Drive**
    ```
> Note In this command, the placeholder **Drive** represents the drive letter of the hard disk to be cleaned.

#### Linux Disk Usage
Disk usage in linux can be monitored using 
`du -h`
If you do not specify the directory, it will default your current one.
If you wanna know how much free space available, you can use-
`df -h`
Defragmentation is not needed in linux, as linux is already good at it.

##### Filesystem repair
###### Windows
When we read or write something to a drive, we actually put it into a buffer, or cache first.
A data buffer is a region of RAM that's used to temporarily store data

while it's being moved around.

So when you copy something from your OS to your USB drive, it first gets copied to

a data buffer because RAM operates faster than hard drives.
So if you don't properly unmount a file system and give your buffer enough time to finish moving data, you run the risk of data corruption.

The NTFS file system has some advanced features built into it that can help minimize the danger of corruption, as well as, try to recover when the file system does get damaged.
One of these features, through a process called journaling, logs changes made to a file metadata into a log file called the NTFS log. By logging these changes, NTFS creates a history of the actions it's taken.
This means it can look at the log to see what the current state of the file system should be. If a crash or bug does cause corruption, the file system can initiate recovery process that will use that log to make sure the system is in a consistent state.

In addition to journaling, NTFS and Windows implements something called self-healing. the self-healing mechanism makes changes to minor problems and corruptions on the disk automatically in the background. It does this while Windows is running so you don't need to perform a reboot.
If you want to check the status of the self-healing process on your computer, you can open up an administrative command prompt and use the fsutil tool
`fsutil repair query C:`

To run check disks manually, you can open up an administrator command prompt and type-
`chkdsk /F D:`

By default, check disk will run in read-only mode. So it'll give you a report on the health of the disk, but won't make any modifications or repairs to it.
You can tell check disk to fix any problems it finds with the /F flag.

###### Linux
[[Linux Filesystem Repair]]