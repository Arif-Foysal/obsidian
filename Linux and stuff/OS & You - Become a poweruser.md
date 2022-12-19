#### Basic Commands
##### Make a directory-
##### Windows
`mkdir directory_name` 
Make a directory that has spaces in between-
`mkdir 'directory name'`
or, seperating with a backtick
```
mkdir directory` name
```
##### Linux
##### Making directory-- same as powershell
Making directory with a space-
`mkdir 'directory name'`
or
`mkdir directory\ name`
#### Command History
##### Windows
view command history -
`history`
Search through command histroy using the shortcut-
Works on #windows as well
`ctrl + R`
History autocompletion (Cycle through matches) - 
`#mkdir 'TAB'`

#### Removing Files and directories
##### Windows
`rm location_to_file`

#### File and Text Manipulation
##### Windows
view the contents of a file 
`cat _file`
View the first 10 line of a file-
`cat _file -Head 10`
 View the last 10 lines of a file-
`cat _file -Tail 10`

View the contents of a file one page at a time (just like the man page)
`more _file`
##### Linux
View the contents of a file,similar to `more` command, but better with vim keybindings and more-
`less _file`

`less` keybindings-
|key |what it does |
|:----:|:----|
|/|searches in the file|
|q|quits to the shell|

Many of the powershell command are Alias of bash commands. To show the original command that gets executed we can use the `Get-Alias` command.
`Get-Alias ls` views the original command of `ls`

There is another type of command called `cmd.exe` that we can use in windows.
`cmd.exe` is old and not as powerful as powershell commands.
|Powershell|Alias|cmd.exe|
|----------|-----|-------|
|Get-Children|ls|dir|
##### Getting help
`Get-Help` is used in #powershell commands like-
`Get-Help ls` 
`/?` is used for other commands such as-
`dir /?`
##### Searching within file
##### Windows
###### Searching using GUI:
By default, windows searches only for indexed properties.
We can change that to `index properties and file contents` by changing the indexing option in control panel > indexing options then selecting the folder we want to change indexing > advanced > file types > 
now change the indexing type

The windows search service should start rebuilding the index. This may take some time.

Done! Try searching using your file explorer.
###### Searching using Command Line
`sls` or Select-String command to find words or other string of characters and files. 
Let's search for the word 'foo' in the file one.txt-
`sls foo one.txt` 
we can also search through through several files in the directory using [[wildcards]]
###### searching for something within directory/filtering
`-Filter` option can be used for this job
ex: Listing all the .exe files in the current directory (including the subdirectory)-
`ls -Recurse -Filter *.exe`

##### Linux
[[Linux For Hackers]]

let's find 'foo' in one.txt -
`grep foo one.txt`
This will output lines that has the string 'foo' in it.
using [[wildcards]] is also allowed
##### Input, Output and Pipeline
###### Windows
Each process in #windows as well as #linux has 3 different streams.
1. stdin (Standard IN)
2. stdout (Standard Out)
3. stderr (Standard Error)

The [redirector operator], `>` allows us change where we want out standard output to go.
|redirector|index|
|----------|-----|
|1>|stdout (**Default**)|
|2>|stderr|

Instead of sending stdout to the screen, we can send stdout to a file.
Ex:
warning: This will overwrite the file if it already exists
`echo hello > hello.txt`
To avoid overwriting and append text to the end of a text file, insted of `>` we can use `>>`

The stdout of `echo hello` is redirected to the file `hello.txt`
###### Sending the output to one command to the input of another command
We can use the pipe `|` operator for this job

Ex:
`cat words.txt | Select-String st`
This will output the lines that has the substring 'st'
We can use output redirection to put our filtered lines into a new file-
`cat words.txt | Select-String st > st_words.txt`

###### Redirecting error messages
we can redirect standard error streams to a file

`rmdir /etc 2> ~/error.txt`

What if we don't care about the error messages and stuff and don't want to put them in a file.

we can redirect standard errors in a `$null`
`rmdir /etc 2> $null`
now our output is filtered out error messages.
##### Linux
Similar to windows, linux has the 3 common I/O streams.
Taking input from a file- we can use the `<` operator-
`cat < file.txt`

There is a special file in linux located in `/dev/null` which is similar to `$null` variable in windows-

`rmdir /etc 2> /dev/null`
Output is filtered from error messages.
###### Piping
Taking the output of one command and redirecting it as stdin to another command
`ls -la | grep bluetooth`
stdout of ls -la will redirected as input of grep command
#### Week 2: Users and permissions
##### Windows
We can manage users and groups both in GUI and CLI. 
###### GUI
We can use the `computer management` tool to view user and group information in windows.
`computer management` can be found using the application search bar of windows.
![[Screenshot_20221209_004817.png]]
Under the system tools, `event viewer` contains system logs.
`shared folder` - manage folders that users of the machine shares with each other.
`Local users and groups`- This is where we manage our users and groups.
The `Administrator` account is disabled by default.
But we can make other users member of administrator group to use administrator power.

###### CLI
View the list of users in the computer-
`Get-LocalUser`

List the groups in the local machine-
`Get-LocalGroup`

View what users in a particular group-
`Get-LocalGroupMember $groupName`
Users that are member of administrator group-
`Get-LocalGroupMember Administrators`

##### Linux
Types of users-
- standard user
- administrator
- root user
[[Linux notion]]

View who has access to run sudo 
`cat /etc/group`

View list of users-
`cat /etc/passwd`

##### Passwords
###### Windows
###### CLI
Change the password of a user-
`net user $username 'password'`
Prompt to enter the password instead of typing in the command (The better approach, cause anyone can find the password from the command history)-

`net user $username *`

Force a user to change password in the next login-

`net user $username /logonpasswordchg:yes`

###### Linux
Change password of a user-
`passwd $username`

Force a user to change password-
-e flag stands for expire
`sudo passwd -e $username`

##### Adding and removing users
###### Windows GUI
computer management tool > Local users and groups > right click > create new user
###### Windows CLI
`net user $username * /add`

> Prompts for the password

Deleting an user account-
`net user $username /del`
or
`Remove-LocalUser $username`
###### Linux
add a user-
`sudo useradd $username`
remove a user-
`sudo userdel $username`
##### Permissions
###### Windiws
In windows, files and directory permissions are assigned using Access Control Lists. To be more specific, we are gonna work with Discretionary Access Control Lists or DACLs.
Windows files and folders can also have System Access Control Lists or SACLs assigned to them.
Managing permissions-
###### GUI
Right click to a file > Properties > Security > edit permissions
###### CLI
We can use a utility called ICACLs (Improved Changed ACLs) to change and view ACLs

`icacls C:\Users\wayne\Desktop\`

##### Linux
To view the permissions of a file/directory, we can use ls with the parameter -l 
`ls -l ~/ss.txt`
op-
```
-rw-rw-r-- 1 mrx mrx 140 Sep 20 18:09 ss.txt
```
here,
```
add details....
```

##### Modifying permission
###### Windows
Gui- properties > security > you know what do do
###### CLI
CMD-
`icacls "C:\Users\Wayne\Desktop" /grant Everyone:(OI)(CI)(R)`

Powershell-
`'icacls C:\Users\Wayne\Desktop' /grant 'Everyone:(OI)(CI)(R)'`

**please study details about windows permissions later**

###### Linux

|Notation| Roles |
|--------|---------|
|u|owner|
|g|group|
|o|other user(all users who are not owner and not part of group)|
|a|all(all 3 roles above)|

**Permission Notations**
|Notation|Permission|
|-----|------|
|r|read|
|w|write|
|x|execute|

**Numeric Representations**
|number|permissions|
|-|:-|
|7|full(rwx)|
|6|read and write(rw-)|
|5|read and execute(r-x)|
|4|read only(r--)|
|3|write and execute(-wx)|
|2|write only(-w-)|
|1|execute only(--x)|
|0|none(---)|
We can modify permissions using `chmod`


**Changing owner of a file**
synopsis-
`chown <user> <file>`

##### Special Permissions
###### GUI
To view special permissions in gui,
properties > security > Advanced
###### Linux
**SetUID, SetGID and sticky bit**
  
**SetUID** - Special permission bit that is used to allow a file to be run as the owner of the file.

**Sticky bit** - It is used to allow anyone to write on a file, but only owner or root can delete the file.

##### Package and software management

##### Package Dependencies
###### Windows
Locate packages along with it's dependencies-
`Find-Package sysinternals -IncludeDependencies`
an error will show up because the default source of packages is the powershell gallery, which doesn't contain sysinternals package.
All we need to to is tell powershell about a place where it can find sysinternals package.
**Adding package source**
`Register-PackageSource -Name chocolatey -ProviderName Chocolatey -Location http://chocolatey.org `
Now we can install sysinternals by the following command-
`Install-Package sysinternals`
We can also specify the ProviderName in case of confliction.
###### Linux
Install dependencies automatically while installing an package-
``
##### Package Management
###### Windows
We can either use the chocolatry command line tool or use the package management feature that was recently released for Powershell.

Using package management tool to install a package from chocolatey repository-
`Install-Package <packageName> -ProviderName Chocolatey`

###### Linux
**Apt package manager**
- Installs dependencies automatically
The repository source file in Ubuntu is `/etc/apt/sources.list`
**PPA** is a software repository foruploading source packages to be built and published as an Advanced Packaging Tool (apt) repository by Launchpad
**Be careful using a ppa repository instead of original developers repo. It can sometime contain malicious  programs**
Launchpad is a website owned by the organization, Canonical Limited. It allows open source developers to develop, maintain and distribute softwares.
Learn more about ppa and launchpad https://help.launchpad.net/Packaging/PPA
###### Underneath the hood 
###### Windows
`orca.exe` is used to create or edit windows installer packages.
https://drive.google.com/file/d/1RnJ0Xi40ZQKbMoVrcbqn9wp2xSqy_LXo/view
orca.exe-
https://learn.microsoft.com/en-us/windows/win32/msi/orca-exe?redirectedfrom=MSDN
process monitors-
https://learn.microsoft.com/en-us/sysinternals/downloads/procmon
Windows Installer Examples-
https://learn.microsoft.com/en-us/windows/win32/msi/windows-installer-examples?redirectedfrom=MSDN

##### Devices and Drivers
Drivers help our hardware devices to interact with our operating system
###### Windows

we can use the `Deviece manager` tool to manage devices and drivers.
When a device is plugged in,  windows asks for it's hardware id and installs appropreate driver for the device to work.


###### Linux
In linux, **everything is considered as a file, even hardware devices.**

When a device is connected to your computer, a device file is created in the `/dev` directory. Let's look into the directory-
`ls -l /dev`

The output will show a lots of files in the directory, but not all of them are actually physical devices.-
There are a lot of device types in liunx. 
Some of them are the following-

- Character Devices
	Character Devices transmits data character by character. Such as keyboard or a mouse.
- Block Devices
	Block Devices transmit data block by block. Such as usb storage.
We can specify the type of device by following the type of file it is.
`ls -l /dev | grep sda`
output-
```
brw-rw----   1 root disk        8,     0 Dec 17 20:15 sda  
brw-rw----   1 root disk        8,     2 Dec 17 20:15 sda2  
brw-rw----   1 root disk        8,     3 Dec 17 20:15 sda3  
brw-rw----   1 root disk        8,     4 Dec 17 20:15 sda4
```
c stands for character device.
b stands for block device.
`sd` devices are mass storage devices like our hard drives, memory cards.

**Updating device drivers in linux**
Device drivers are stored in the /dev directory. Sometimes they're part of kernel.
If there are devices that doesn't have support built into the kernel, they most likely have something called `Kernel module`. 
`Kernel Module` extends the kernels functionality without them actually touching it.
`kernel module` for a specific device can be installed same way as installing any software. 
Not all `kernel modules` are drivers.
[[Linux Devices and Drivers]]

