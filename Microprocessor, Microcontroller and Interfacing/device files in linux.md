#linux #interfacing #Microprocessor 

In Linux, the `/dev` directory is a special directory that contains device files, also known as device nodes. These device files are used to interface with and communicate with hardware devices, including disk drives, input/output devices, network interfaces, and other hardware components.

## Listing /dev path for each device
**ref:** https://unix.stackexchange.com/questions/144029/command-to-determine-ports-of-a-device-like-dev-ttyusb0

```bash
for sysdevpath in $(find /sys/bus/usb/devices/usb*/ -name dev); do
    (
        syspath="${sysdevpath%/dev}"
        devname="$(udevadm info -q name -p $syspath)"
        [[ "$devname" == "bus/"* ]] && exit
        eval "$(udevadm info -q property --export -p $syspath)"
        [[ -z "$ID_SERIAL" ]] && exit
        echo "/dev/$devname - $ID_SERIAL"
    )
done
```

which outputs the following-
```bash
/dev/input/event12 - RAPOO_Rapoo_2.4G_Wireless_Device  
/dev/input/event9 - RAPOO_Rapoo_2.4G_Wireless_Device  
/dev/input/mouse2 - RAPOO_Rapoo_2.4G_Wireless_Device  
/dev/input/event11 - RAPOO_Rapoo_2.4G_Wireless_Device  
/dev/input/event10 - RAPOO_Rapoo_2.4G_Wireless_Device  
/dev/input/event13 - SIGMACHIP_Usb_Mouse  
/dev/input/mouse3 - SIGMACHIP_Usb_Mouse  
/dev/video1 - Azurewave_USB2.0_VGA_UVC_WebCam_0x0001  
/dev/video0 - Azurewave_USB2.0_VGA_UVC_WebCam_0x0001  
/dev/input/event15 - Azurewave_USB2.0_VGA_UVC_WebCam_0x0001
```

An improved script for this job-
```bash
#!/bin/bash                                                            
#findusbdev.sh
if [[ "$1" =~ ^(-h|--help)$ ]]; then                                   
echo "Find which USB devices are associated with which /dev/ nodes     
Usage:                                                                 
  $0 [-h|--help] [searchString]                                        
                                                                       
  -h | --help   Prints this message                                    
  searchString  Print only /dev/<device> of matching output            
                With no arguments $0 prints information for all        
                possible USB device nodes                              
E.g. $0 \"FTDI_FT232\" - will show /dev/ttyUSBX for a device using     
the FTDI FT232 chipset.                                                
"                                                                      
    exit 0                                                             
fi                                                                     
devs=$( (                                                              
for sysdevpath in $(find /sys/bus/usb/devices/usb*/ -name dev ); do    
    # ( to launch a subshell here                                      
    (                                                                  
        syspath="${sysdevpath%/dev}"                                   
        devname="$(udevadm info -q name -p $syspath)"                  
        [[ "$devname" == "bus/"* ]] && exit                            
        eval "$(udevadm info -q property --export -p $syspath)"        
        [[ -z "$ID_SERIAL" ]] && exit                                  
        echo "/dev/$devname - $ID_SERIAL"                              
    )& # & here is causing all of these queries to run simultaneously  
done                                                                   
# wait then gives a chance for all of the iterations to complete       
wait                                                                   
# output order is random due to multiprocessing so sort results        
) | sort )                                                             
if [ -z "$1" ]; then                                                   
    echo "${devs}"                                                     
else                                                                   
    echo "${devs}" | grep "$1" | awk '{print $1}'                      
fi                                                                     
```
