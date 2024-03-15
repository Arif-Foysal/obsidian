#nodemcu #esp8266 

**ref:** https://www.embedded-robotics.com/esp8266-wifi/

We can program the board in two modes-
	1. **Station (STA) Mode**
	2. **Access Point (AP) Mode**

## Station (STA) Mode
In station mode, ESP8266 will act just like your smartphone or laptop. It will connect to an **existing WiFi channel**, or in most cases, the WiFi advertised by your router.

Once you have programmed ESP8266 in STA mode and you are successfully connected to stable WiFi, you can access any web page on the internet.
![[sta mode.png]]

## Access Point (AP) Mode
In AP mode, the ESP8266 itself acts as a Wi-Fi access point or hotspot. Other smart devices will be able to connect, and consequently establish communication with the [[nodemcu esp8266]] WiFi module.
In this case, ESP8266 won’t be able to access the internet as it is merely advertising a WiFi hotspot. Besides, the devices connected to the WiFi advertised by ESP8266 will only be able to communicate with ESP8266 and not with any web server.
![[esp8266 access point mode.png]]