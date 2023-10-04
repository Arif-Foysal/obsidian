>[!Contents]
	> [[#Linux Filesystem]]
	> [[#Searching/Finding stuff in Linux]]

## **Linux Filesystem**
|**Path**|**Description**|
|-------|--------|
| `/`  | Root directory, The home directory for all root users  |
|  `/etc` | Generally contains Linux configuration files, files that control how and when pograms start up. Configuration files from installed applications may be saved here as well.  |
|  `/home` |  Each user has a subdirectory here for storage |
|  `/mnt` | Where other filesystems are attached or mounted to the system  |
|  `/media` | External removable media devices such as USB drives are mounted here.  |
|  `/bin` | Where application binaries are stored  |
|  `/lib` | Shared library files that are required for system boot.  |
|  `/tmp` |  The operating system and many programs use this directory to store temporary files. This directory is generally cleared upon system boot and may be deleted at other times without any warning. |
|  `/usr` | Contains executables, libraries,man files etc  |
## Searching/Finding stuff in Linux
### **The `locate` command**
**Synopsis-**
`locate [OPTION]... PATTERN...`
This command goes through entire filesystem and locates every occerances of that pattern.
**Downsides-**  
- Results can be overwelming, giving too much information. 
- It uses a database that updates once a day. You may not find a file that was created a minute ago.

### **Finding Binaries and man page with `whereis`**
**Synopsis-**
`whereis [options] [-BMS <dir>... -f] <name>`
If you are looking for a binary, this might be the command to locate it. It returns not only the binary but also it's source and man page if available.
**Example-**
kali>`whereis bash`
bash: `/usr/bin/bash /usr/share/man/man1/bash.1.gz`
		*binary*         *man page*

### **Finding binaries with `which`**
**Synopsis-**
`which [-a] filename ...`
It only returns the location of the binaries in the path variable in linux.
**Example-**
kali>`which bash`
bash: `/usr/bin/bash`


### **More powerful search using `find`**
**Synopsis-**
`find  [-H]  [-L]  [-P]  [-D  debugopts]  [-Olevel] [starting-  point...] [expression]`
informal syntax-
`find directory options expression`

**Example**
kali> `find /home/mrx -type f -name freecodeCamp.png`
bash: `/home/mrx/Certifications/FreeCodeCamp.png`
**Downsides**
- only outputs the exact matches. Even if the searched file has an extension, it will not find a match.
**sol:** We can easily solve this problem by using [[Bash Wildcards]]. Wildcard come in a few different forms such as: * . ? and [ ]



## **Chapter 2: Text Manipulation**







