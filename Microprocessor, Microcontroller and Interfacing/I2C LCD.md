#display #lcd #Microcontroller #Microprocessor 

ref: https://lastminuteengineers.com/i2c-lcd-arduino-tutorial/

# Programming I2C LCD Display
### Interfacing with [[arduino]]

|                | SCL | SDA |
| -------------- | --- | --- |
| Arduino Uno    | A5  | A4  |
| Arduino Nano   | A5  | A4  |
| Arduino Mega   | 21  | 20  |
| Leonardo/Micro | 3   | 2   |
|                |     |     |

### Interfacing with [[nodemcu esp8266]]

|                 | SCL | SDA |
| --------------- | --- | --- |
| Nodemcu Esp8266 | D1  | D2  |


### Installing required library

You'll need to install `LiquidCrystal I2C` library by Frank de Brabander from library manager (sketch > include library > manage libraries). 
Or you can download the zip file of the library from here -

https://www.arduino.cc/reference/en/libraries/liquidcrystal-i2c/

### Determining i2c address
the I2C address of your LCD depends on the manufacturer. If your LCD has a PCF8574 chip from Texas Instruments, its I2C address is 0x27; if it has a PCF8574 chip from NXP Semiconductors, its I2C address is 0x3F.
If you’re not sure what your LCD’s I2C address is, you can run a simple I2C scanner sketch that scans your I2C bus and returns the address of each I2C device it finds.
You can find this sketch under **File** > **Examples** > **Wire** > **i2c_scanner**.
```c++
#include <Wire.h>

void setup() {
  Wire.begin();

  Serial.begin(9600);
  while (!Serial); // Leonardo: wait for serial monitor
  Serial.println("\nI2C Scanner");
}

void loop() {
  int nDevices = 0;

  Serial.println("Scanning...");

  for (byte address = 1; address < 127; ++address) {
    // The i2c_scanner uses the return value of
    // the Write.endTransmisstion to see if
    // a device did acknowledge to the address.
    Wire.beginTransmission(address);
    byte error = Wire.endTransmission();
    if (error == 0) {
      Serial.print("I2C device found at address 0x");
      if (address < 16) {
        Serial.print("0");
      }
      Serial.print(address, HEX);
      Serial.println("  !");

      ++nDevices;
    } else if (error == 4) {
      Serial.print("Unknown error at address 0x");
      if (address < 16) {
        Serial.print("0");
      }
      Serial.println(address, HEX);
    }
  }
  if (nDevices == 0) {
    Serial.println("No I2C devices found\n");
  } else {
    Serial.println("done\n");
  }
  delay(5000); // Wait 5 seconds for next scan
}
```
In serial monitor, i found the address `0x27`-
```
Scanning...

I2C device found at address 0x27  !

done
```

You may need the address later.

### Printing to the lcd display

The following code prints- 
```
Hello world
LCD Tutorial
```
on the display.
**Code:**
```c++
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x27,16,2); // set the LCD address to 0x27 for a 16 chars and 2 line display

void setup() {

lcd.init(); //initialize the

lcd.clear(); //clar the lcd screen

lcd.backlight(); // Make sure backlight is on

// Print a message on both lines of the LCD.

lcd.setCursor(2,0); //Set cursor to character 2nd column on line 0

lcd.print("Hello world!");

lcd.setCursor(2,1); //Move cursor to character 2nd column on line 1

lcd.print("LCD Tutorial");

}

void loop() {

}
```
>[!note]
>Replace the i2c address with your specific one.

# Menu Using i2c LCD

<iframe width="560" height="315" src="https://www.youtube.com/embed/DuAG98P9Seo?si=Adb8YlOb2wn1Zs-c" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
