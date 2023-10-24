#Microprocessor #project #uiu #Computer-Science #electronics #research 

>[!Index]
>### [[underwater rov#Literature Review|Literature Review]]
>- [[underwater rov#Bracu Duburi AUV|Bracu Duburi AUV]]
>### [[underwater rov#Chassis|Chassis]]
>
>### [[underwater rov#Communication between microcontrollers|Communication between microcontrollers]]
>- [[nodemcu esp8266]]
>	- [[nodemcu esp8266- getting the mac address]]
>	- [[nodemcu esp8266 transmitter and receiver]]
>	- 

# Literature Review

>[!Note]
>PDF of each paper is uploaded on the google drive folder.

## Bracu Duburi AUV
ref: https://bracu-duburi.com

### Duburi 3.0

**Key takeaways**
- ==Design of the arm== 
- They copied the design from blue robotics's rov.
	Blue robotics rov: https://www.youtube.com/watch?v=Mgwn1sR-6g8
![[Pasted image 20231012145648.png|400]]
### Duburi 1.0
## Design and construction of an ROV for underwater exploration

**doi:** ==10.3390/s19245387==


**Key Takeaways**
- They used brushless motors for thrusters.
- They used relays to change direction of the brushless motors.
- Speed controllers has been used to control speed of brushless motors. (**not cheap**)

![[Screenshot_20231012_181346.png]]

## Riasat khan- Semi Wireless Underwater Rescue Drone with robotic arm (they're from NSU)
**doi:** 10.18196/jrc.v3i4.14867









# Communication between microcontrollers

We are using two [[nodemcu esp8266]] for wirelessly communicating between the controller and the receiver on the rover.
We need a communication protocol that will allow us to control the rover remotely with the controller, as well as receive data from the rover e.g. sensor data, gyroscope data.
[[espnow]] protocol is being used for the peer-to-peer communication, since [[espnow]] supports both one way and two way communication. So here is a brief introduction of how to program [[nodemcu esp8266]] and how to establish two way communication using [[espnow]] protocol.

![[nodemcu esp8266]]

Now that we have established two way communication between our two nodemcu's, now we have to establish serial communication between the receiver nodemcu board and [[arduino]] mega since we want to control all the actuator. 
The receiver would receive commands from the physical controller and forward it to the [[arduino]] mega. At the same time the mega would forward it's sensor readings to the receiver through serial, and the receiver would send all the sensor data to the controller. Here is how serial communication between [[nodemcu esp8266]] and [[arduino]] is done-
![[serial communication between arduino and nodemcu]]

# Chassis

# Thrusters

## Motors

# Arm
## Actuators


# Q/A
1. Should we thrust to lift the rover upwards (if initially the rover would sink), or push the rover down (the rover floats initially)?

**More References:**
6DOF (degree of freedom): https://www.ardusub.com/introduction/features.html

