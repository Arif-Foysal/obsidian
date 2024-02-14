#ip #nodemcu #computernetworks 

**ref:** https://arduino-esp8266.readthedocs.io/en/latest/esp8266wifi/readme.html

```cpp
#include <ESP8266WiFi.h>
void setup()
{
Serial.begin(9600);
Serial.println();
WiFi.begin("Sobuz bangla", "Aman4811");
Serial.print("Connecting");
while (WiFi.status() != WL_CONNECTED)
{
delay(500);
Serial.print(".");
}
Serial.println();
Serial.print("Connected, IP address: ");
Serial.println(WiFi.localIP());
}
void loop() {}
```

**Related Links**
[[mac address]]
[[ip addressing]]
[[nodemcu esp8266]]
