#nodemcu #Microprocessor #Microcontroller 

>[!Index]
>

[[esp wifi modes]]
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

## Required libraries
#libraries

1. **ESP8266WiFi**
	Documentation: https://arduino-esp8266.readthedocs.io/en/latest/esp8266wifi/readme.html

2. **WiFi**
	Download: https://www.arduino.cc/reference/en/libraries/wifi/
	Documentation: 
## Pinout

![[Pasted image 20231011172059.png]]

![[esp8266-pinout.png]]

## esp8266 Transmitter and Receiver
![[nodemcu esp8266 transmitter and receiver]]
## Getting the [[mac address]]

![[nodemcu esp8266- getting the mac address]]

## Getting the IP address

![[nodemcu esp8266- getting the ip address]]

**Related Links**
[[device files in linux]]




