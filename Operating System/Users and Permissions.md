#### Managing Users
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

#### Passwords
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

#### Adding and removing users
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
#### Permissions
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

#### Modifying permission
###### Windows
Gui- properties > security > you know what do do
###### CLI
CMD-
`icacls "C:\Users\Wayne\Desktop" /grant Everyone:(OI)(CI)(R)`

Powershell-
`'icacls C:\Users\Wayne\Desktop' /grant 'Everyone:(OI)(CI)(R)'`

**please study details about windows permissions later**

###### Linux

|Notation|Roles|
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
|------|-----------|
|7|full(rwx)|
|6|read and write(rw-)|
|5|read and execute(r-x)|
|4|read only(r--)|
|3|write and execute(-wx)|
|2|write only(-w-)|
|1|execute only(--x)|
|0|none(---)|
We can modify permissions using `chmod`

**Checking permissions of a directory:**
```bash
ls -ld /var/www/html/test
```
Output should look like this:
```
drwxr-xr-x 2 www-data www-data 4096 Aug 19 12:34 /var/www/html/test
```
- **`drwxr-xr-x`**: This string represents the permissions of the directory.
    - **`d`**: Indicates that it's a directory.
    - **`rwx`**: The owner (`www-data`) has read (`r`), write (`w`), and execute (`x`) permissions.
    - **`r-x`**: The group (`www-data`) has read (`r`) and execute (`x`) permissions, but not write.
    - **`r-x`**: Others (everyone else) have read (`r`) and execute (`x`) permissions, but not write.
- **`2`**: Number of hard links to the directory.
- **`www-data www-data`**: The first `www-data` is the owner of the directory, and the second `www-data` is the group associated with it.
- **`4096`**: The size of the directory in bytes.
- **`Aug 19 12:34`**: The last modification date and time.
- **`/var/www/html/test`**: The directory path.

### Breakdown of Permissions:

- **Read (`r`)**: Allows viewing the contents of the directory.
- **Write (`w`)**: Allows creating, deleting, or modifying files within the directory.
- **Execute (`x`)**: Allows entering the directory (cd into it) and accessing its contents.

### Understanding Permission Codes:

- **`rwxr-xr-x`** is broken down as follows:
    - **Owner (first three characters)**: `rwx` - the owner can read, write, and execute.
    - **Group (next three characters)**: `r-x` - the group can read and execute, but not write.
    - **Others (last three characters)**: `r-x` - others can read and execute, but not write.

## Changing owner of a file
synopsis-
`chown <user> <file>`

#### Special Permissions
###### GUI
To view special permissions in gui,
properties > security > Advanced
###### Linux
**SetUID, SetGID and sticky bit**
  
**SetUID** - Special permission bit that is used to allow a file to be run as the owner of the file.

**Sticky bit** - It is used to allow anyone to write on a file, but only owner or root can delete the file.
