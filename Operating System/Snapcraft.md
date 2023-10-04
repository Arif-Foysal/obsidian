### Prevent repository packages from triggering installation of snap
1.  The file prevents installation of snap
 ```bash
#crate a file on /etc/apt/preferences.d named nosnap.pref
nano /etc/apt/preferences.d/nosnap.pref 
```
2. Write the following to the file-

```bash
#To prevent repository packages from triggering the installation of Snap,
#this file forbids snapd from being installed by APT.
#For more information: https://linuxmint-user-guide.readthedocs.io/en/latest/snap.html
Package: snapd
Pin: release a=*
Pin-Priority: -10
```
---
