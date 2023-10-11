#Microprocessor #Microcontroller 
## Setup and program esp8266
### Install Driver
The necessary drivers for esp8266 are pre-installed in Linux.
### Install boards manager

https://github.com/esp8266/Arduino

**Open Arduino IDE**
Files > Preferences > Additional boards manager URLs > `paste following link`
```
https://arduino.esp8266.com/stable/package_esp8266com_index.json
```

You can add multiple URLs, separating them with commas.

**Go to**
Tools > Board > Boards Manager > search for esp8266 and install the package

Don't forget to select your ESP8266 board from 
Tools > Board > NodeMCU 1.0 (ESP-12E Module) 
after installation.

### Programming with Linux
Default Port: `/dev/ttyUSB0`
To list out the USB-Serial ports that are active:
```bash
ls /dev/ttyUSB*
```
## Pinout

![[Pasted image 20231011172059.png]]

![[Pasted image 20231011171831.png]]

**Related Links**
[[device files in linux]]




