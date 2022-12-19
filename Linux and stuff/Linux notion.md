[[File management]]

## Managing Users

### Adding user- adding a user named thor

```bash
sudo adduser thor 
#or,
sudo useradd ironman #Downsides of useradd-
#skips password, full name and other entries
#default shell is /bin/sh
#does not have a home directory for the user
```

### List Users in the system

```bash
cat /etc/passwd
```

Output will look like this-

```bash
thor:x:1001:1001:thor-h,,,:/home/thor:/bin/bash
#username:x:UID:GID:fullname of user:home directory:default shell directory
#x-indicates this users password is stored in /etc/shadow
#UID=User id
#GID=Group id
```

When we create an user, we also create a group for that user. In this case our user thor has a group id of 1001

### User modification

```bash
#Modifying users name
sudo usermod tony ironman #usermod old_username new_username
  
```

## Hibernation

### Enable hibernation using existing swap partition

1. Find the UUID of your swap file by running-

```bash
sudo blkid | grep swap
```

output should look like this-

```bash
/dev/sda2: UUID="4561fd18-80dc-433d-adae-2ad1f2fa47a2" TYPE="swap" PARTUUID="5ef1ca33-2f17-44f4-800d-c8da235b4f14”
```

1. Edit the grub file located in /etc/default/grub and add the UUID in after quiet splash

```bash
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash resume=UUID="4561fd18-80dc-433d-adae-2ad1f2fa47a2""
```

1. Update grub by running

```bash
sudo update-grub
```

1. Run the following command and see if hibernation is working

```bash
sudo systemctl hibernate
```

### What i did for ‘hibernate status button’ to work in gnome

1. Enter terminal as root (sudo will not work). Open (or create) a file with:
`nano /var/lib/polkit-1/localauthority/10-vendor.d/com.ubuntu.desktop.pkla`

Add the text below at the end of the file:

```
##NEW entry since Ubuntu 18:
[Re-enable hibernate by default in upower]
Identity=unix-user:*
Action=org.freedesktop.upower.hibernate
ResultActive=yes

##NEW entry since Ubuntu 18:
[Re-enable hibernate by default in logind]
Identity=unix-user:*
Action=org.freedesktop.login1.hibernate;org.freedesktop.login1.handle-hibernate-key;org.freedesktop.login1;org.freedesktop.login1.hibernate-multiple-sessions;org.freedesktop.login1.hibernate-ignore-inhibit
ResultActive=yes

```

1. Clean up hook (Error - recordfail after resume from hibernate). That error occurs after resume (Ubuntu really doesn't want you to hibernate):
`sudo nano /etc/systemd/system/use-10_grub_common.service`
Enter:

```
[Unit]
Description=Execute the /etc/pm/sleep.d/10_grub_common script after hibernation.
After=hibernate.target

[Service]
Type=oneshot
ExecStart=/etc/pm/sleep.d/10_grub-common thaw

[Install]
WantedBy=hibernate.target

```

This script will remove an error flag from grub, preventing it 
showing an error the next time you boot. Since it is a service you need 
to enable it:

`sudo systemctl enable use-10_grub_common`

Ref: [https://askubuntu.com/questions/1405990/hibernate-entry-in-the-menu-on-22-04](https://askubuntu.com/questions/1405990/hibernate-entry-in-the-menu-on-22-04)


## Mounting Cloud Storage's

Mount onedrive via rclone

```bash
rclone --vfs-cache-mode writes mount onedrive: ~/OneDrive
```
 
## Cheat sheet
[[HackTheBox Academy]]
