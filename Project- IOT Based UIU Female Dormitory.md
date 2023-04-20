- Enter RFID > if rfid matched
- Select Items
- Rotate Corresponding servo motors
[[Tasks]]

### UID of Cards
card1: 3175175170169
card2: 1952401243081
tag: 11552120165154
### Pinout
PINOUT:

|RC522 MODULE| Uno/Nano| MEGA|
|------|------|---------|-----|
|SDA| D10| D53|
|SCK| D13 |D52|
|MOSI| D11| D51|
|MISO |D12| D50|
|IRQ| N/A| N/A|
|GND |GND |GND|
|RST| D9 |D5|
|3.3V |3.3V |3.3V|

### Code with credit to corresponding ID:
```
#include <SPI.h>

#include <MFRC522.h>

#include <Servo.h>

#define SS_PIN 53

#define RST_PIN 5

// int card_pin = 6;

// int ring_pin = 7;

  
  

//servos

Servo s1;

bool s1is180=false;

//Vending

int button_wait_time=10000;

  
  
  

//buTTONS

int button1Pin=2;

int button2Pin=3;

int button1State=0;

int button2State=0;

  

class Card {

public:

String uid;

int credits;

};

  

Card authorized_cards[] = {

{"03 AF AF AA", 10}, // uid and corresponding credits

{"73 34 78 A5", 5} // of authorized cards

};

  

int num_authorized_cards = sizeof(authorized_cards)/sizeof(authorized_cards[0]);

  

MFRC522 mfrc522(SS_PIN, RST_PIN);

  

void setup()

{

Serial.begin(9600);

SPI.begin();

mfrc522.PCD_Init();

Serial.println("Scan your ID to begin purchase");

Serial.println();

// pinMode(card_pin, OUTPUT);

// pinMode(ring_pin, OUTPUT);

pinMode(button1Pin, INPUT);

pinMode(button2Pin, INPUT);

s1.attach(9);

if (s1.read() > 90) {

s1.write(180);

s1is180=true;

}

else if (s1.read()<90) {

s1.write(0);

}

else {

s1.write(0);

}

}

  
  

void loop()

{

if (!mfrc522.PICC_IsNewCardPresent())

{

return;

}

if (!mfrc522.PICC_ReadCardSerial())

{

return;

}

Serial.print("UID tag :");

String content = "";

byte letter;

for (byte i = 0; i < mfrc522.uid.size; i++)

{

Serial.print(mfrc522.uid.uidByte[i] < 0x10 ? " 0" : " ");

Serial.print(mfrc522.uid.uidByte[i], HEX);

content.concat(String(mfrc522.uid.uidByte[i] < 0x10 ? " 0" : " "));

content.concat(String(mfrc522.uid.uidByte[i], HEX));

}

Serial.println();

content.toUpperCase();

boolean is_authorized = false;

int credits = 0;

for (int i = 0; i < num_authorized_cards; i++) {

if (content.substring(1) == authorized_cards[i].uid) {

is_authorized = true;

credits = authorized_cards[i].credits;

break;

}

}

if (is_authorized)

{

Serial.print("Welcome. Your available credit is: ");

Serial.print(credits);

Serial.println(" credits");

// digitalWrite(6, HIGH);

delay(1000);

// digitalWrite(6, LOW);

Serial.println("Please select your item...");

int button_timer_start=millis();

int button_pressed=0;

while (button_pressed==0){

int button_timer_current=millis();

if (button_timer_current>=button_timer_start+button_wait_time) {

break;

}

if (digitalRead(button1Pin) == HIGH) {

button_pressed=1;

}

} // wait for button1 press for 10 sec

if (button_pressed==0) {

Serial.println("Timeout!");

}

if (button_pressed!=0) {

if (s1is180) {

s1.write(0);

s1is180=false;

} else {

s1.write(180);

s1is180=true;

}

Serial.println("Thank you for your purchase");

}

  

}

else

{

Serial.println("Access denied");

delay(1000);

}

}
```
