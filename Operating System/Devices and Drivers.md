
##### Introduction to Devices and Drivers 
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

