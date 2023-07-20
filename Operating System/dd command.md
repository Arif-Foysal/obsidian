Determine the device name of your USB flash drive by running the following command:

-   `sudo fdisk -l`
    
    This will display a list of all the storage devices connected to your computer. Identify the device name of your USB flash drive (e.g., `/dev/sdb`).
    
-   Unmount the USB flash drive by running the following command (replace `/dev/sdb` with the device name you identified in step 3):
    
    bash
    
-   `sudo umount /dev/sdb`
    
-   Use the `dd` command to copy the contents of the ISO image to the USB flash drive:
    
    bash
    
-   `sudo dd bs=4M if=/path/to/your/iso/file.iso of=/dev/sdb status=progress && sync`
    
    Here, replace `/path/to/your/iso/file.iso` with the path to the ISO image file you want to write to the USB flash drive, and replace `/dev/sdb` with the device name you identified in step 3.
    
    The `bs=4M` option specifies the block size to use when copying data. The `status=progress` option will display the progress of the write operation.
    
-   After the `dd` command finishes running, use the `sync` command to ensure all data has been written to the USB flash drive:
    
    bash
    

1.  `sync`
    
2.  Eject the USB flash drive from your computer and it should be ready to use as a bootable device.
    

Note: Be careful when specifying the device name in step 5, as choosing the wrong device could cause you to overwrite important data on your system. Double-check the device name before running the `dd` command.