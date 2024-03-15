#networking 

The **Open System Interconnection(OSI)** model, created in 1984 by ISO, is a reference framework that explains the process of transmitting data between computers. It is divided into 7 layers that work together to carry out specialised network functions, allowing for a more systematic approach to networking.

![[osi layers.png]]

## 7 Layers of OSI Model

1. [[application layer]]
2. [[presentation layer]]
3. [[session layer]]
4. [[transport layer]]
5. [[network layer]]
6. [[data link layer]]
7. [[physical layer]]

## Advantages of OSI Model

OSI Model defines the communication of a computing system into 7 different layers. Advantages of OSI Model include:

- It divides network communication into 7 layers which makes it easier to understand and troubleshoot.
- It standardizes network communications, as each layer has fixed functions and protocols.
- Diagnosing network problems is easier with the OSI model.
- It is easier to improve with advancements as each layer can get updates separately.

## OSI model in a nutshell

|****Layer No****|****Layer Name****|****Responsibility****|****Information Form(Data Unit)****|****Device or Protocol****|
|---|---|---|---|---|
|7|Application Layer|Helps in identifying the client and synchronizing communication.|Message|SMTP|
|6|Presentation Layer|Data from the application layer is extracted and manipulated in the required format for transmission.|Message|JPEG, MPEG, GIF|
|5|Session Layer|Establishes Connection, Maintenance, Ensures Authentication and Ensures security.|Message|Gateway|
|4|Transport Layer|Take Service from Network Layer and provide it to the Application Layer.|Segment|Firewall|
|3|Network Layer|Transmission of data from one host to another, located in different networks.|Packet|Router|
|2|Data Link Layer|Node to Node Delivery of Message.|Frame|Switch, Bridge|
|1|Physical Layer|Establishing Physical Connections between Devices.|Bits|Hub, Repeater, Modem, Cables|