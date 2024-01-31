#rov #robotics #underwater #Microcontroller #Microprocessor #arduino #raspberrypi 

# Documentary Script
On our planet, with oceans covering over 70% of the surface, there's a vast, unexplored world beneath the waves. As a species, we have reached the outer edges of our solar system, yet the mysteries beneath the waves remain largely unknown. In fact, we have explored more of space than the oceans of our own planet.

Yet, we've only scratched the surface. Understanding the oceans is crucial for our planet's health and the survival of countless species.

Exploring underwater with human divers is tough and costly. The unpredictability of the underwater environment presents logistical challenges, risking the safety of specially trained divers. The expenses and dangers have led us to search for safer and more cost-effective exploration methods.



**Newer**
Underwater exploration can be extremely expensive and risky. With the help of modern technology, we can deploy underwater ROVs instead of human divers as a safer and more cost effective option. 


Blue Horizon is an underwater Rover capable of underwater exploration, research, and rescue operations. The project was developed by a team of six students studying in the Computer Science and Engineering department at United International University. The team participated in the UIU CSE Project Show 2023 and won the title of CHAMPIONS in the Microprocessor, Microcontrollers and Interfacing Lab. The team members have a broad range of experience in mechanical , software, electronics, and communication fields.
**Mechanical**
Designing: - The **commercial** underwater thrusters costs around $200, which is very expensive. So we decided to use **brushless** motors and designed our own 3D-printed **thrusters** that worked perfectly for our needs. The configuration of 6 thrusters allows the rover to have four degrees of freedom. This gives us **complete control** over the ROV and enables us to maneuver it in any direction including forward, backward, up, down, roll, and yaw. Moreover, we built a 3d model of the chassis before actually building it to understand better how the final product will look and function.
 Fabrication: - To build the chassis, we used PVC pipes, which is a strong and durable material. We cut and assembled the PVC pipes and fittings to create the framework of the ROV. To make the chassis waterproof, we used silicon and epoxy resin. We applied multiple silicon layers on the joints of the front glass and connections to seal any gaps and prevent water from seeping in. We also coated the inner and outer joints with epoxy resin to add an extra layer of protection against water damage.

**Electronics, Software and Communication**

Being able to control the rover **remotely** is one of the key features of the project. We have built a wireless transceiver to control the ROV from a distance.
The movement of the ROV is controlled by push buttons on the controller and the arm is controlled by a potentiometer.

To control the arm of the ROV, the analog values of the potentiometer are converted to digital and then mapped according to the range of values for which the servo motor of the arm is fully opened to fully closed.

ESP-NOW communication protocol has been used to achieve fast and reliable wireless communication between the controller and the receiver of the rover. A two-way communication has been established to send control commands and receive sensor data from the rover simultaneously.
Apart from the arm control, we have also incorporated a menu on the controller which is displayed on an I2C LCD display. From the menu, the modes of the rover can be changed. The modes are Normal, Sports, and Custom. In Sports mode, the ROV increases its speed while moving forward or backward. In Custom mode, the speed of the thrusters can be adjusted to suit the user's preference. Moreover, we have also integrated an LED on the ROV to overcome the limited visibility in the depths of the water, which can be turned on or off from the controller menu.

Due to the fact that Radio waves have difficulty traveling through water due to the high absorption of electromagnetic signals in this medium, we have placed the receiver inside a waterproof container that floats on water, and the receiver talks to the Arduino on the rover via serial communication through an Ethernet cable. 

The rover is powered by a 3-cell Lithium polymer battery. To ensure emergency shutdown, a kill switch has been incorporated within the receiver box along with the battery.
We have built a custom power distribution board to distribute required voltages among the electronics.The Raspberry Pi that has been interfaced with a Raspberry Pi camera for live streaming from the rover is powered by a step-down buck converter. All the wiring and connections have been soldered properly and then coated with hot glue to prevent any potential short circuit. To stream live camera from the raspberry pi, a flask web server is created and initiated on the local server of the router to which the Raspberry Pi is connected via Ethernet.

**Missing:** Gyroscope




**Mission**

With everything in place, the team deploys the rover for a mission in a nearby swimming pool and begins to control it from the remote controller. As the rover approaches the ID card, the team carefully grab the card and secure it. Now that we have the payload, the rover is maneuvered on it's way back to its initial starting point. Mission accomplished.

**Concltsion**

I would like to thank our honorable faculty mr. fahim hafiz, who has supported and motivated the team throughout the journey. 

This project would not be possible without the invaluable contributions of my team: Mohaiminul Haque's electrical brilliance, Ifat Hasan's expertise in electrical components, and my own role in embedded software and communication. Shahriar Fardin's mechanical expertise, Kawsar Ahmed's software skills, and Akibul Hasan's electrical proficiency have collectively shaped our project. Grateful for this dynamic team that brought diverse skills to elevate our project to new heights.

A huge shoutout to every members of the team for their hard work and dedication to this project.
Thank you for watching the video, and we hope you enjoy our demonstration of our project.




We are not done with the project yet. We are planning to improve the project and make it autonomous by the next year.
