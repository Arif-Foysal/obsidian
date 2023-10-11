#nodemcu #esp8266 #Microprocessor 



**ref:** https://randomnerdtutorials.com/get-change-esp32-esp8266-mac-address-arduino/


```cpp
#ifdef ESP32
#include <WiFi.h> //if the board is esp32, include this library
#else
#include <ESP8266WiFi.h> //else, include this library 
#endif

void setup(){
Serial.begin(9600);
Serial.println();
Serial.print("ESP Board MAC Address: ");
Serial.println(WiFi.macAddress());
}

void loop(){


}
```

### mac address of my nodemcu 8266
```
C8:2B:96:1C:FE:67
```

**Related Links**
[[mac address]]
[[underwater rov]]
[[underwater rov literature review]]
[[nodemcu esp8266]]
