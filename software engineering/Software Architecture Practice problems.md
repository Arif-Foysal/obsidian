
Faculty: FTU
## CT

### CT1
1. (8 points ) A grade calculator takes into account a student’s attendance counts, GPA in each course, and behavior points, which is calculated in each trimester. 
    

Behavior point = (total attendance counts - 5 + base behavior point) / number of credits enrolled for the trimester There are 50 thousand students in the university. The system calculates behavior points for the students one by one. Once this behavior point calculation starts it’s expected to take 50 minutes. The system administrator for the behavior point system has found the following anomalies, Find out the tactics to recover from these

1. The system freezes often after getting stuck in the process, resulting from some mathematical errors / the ALU not being available / cooling system being incapacitated. 
    
2. The system often tries to calculate the behavior point before the base behavior point is available
    

B) [1 points] The grade calculator expects 97% availability. What will be the downtime in a decade? 

C) [1 points] The grade calculator faces failure every 1 year and it takes 5 minutes to get the system back in working order. What’s the availability of this system?


### CT2
1. [6 points] Arthur is using a state-of-the-art sensor to detect herbivorous animal movement in his garden. The sensor takes 5 minutes to become operational after being powered on. Since 5 minutes is enough time for the animals to cause harm, Arthur needs the movement data continuously, with no downtime. Despite its advanced technology, the sensor is prone to errors and often exhibits anomalous behavior. Additionally, it can fail suddenly without any warning. To address these issues, Arthur is considering using multiple sensors to ensure that if one malfunctions or fails, the others can continue to function effectively. Clearly, Arthur is addressing availability issues. Elaborate on which availability tactics he should be using.
    
2. [4 points] John has published an e-commerce app, but customer dissatisfaction has arisen due to a newly introduced lottery feature. Stakeholders have decided to remove this feature. Since John did not provision for a feature toggle, he must update the app to remove the lottery feature. This presents a challenge because the backend lottery system must remain operational during the update process, as not all customers will update the app simultaneously. What deployability tactics should he use?

### CT3
1. [ 2 points ]  
    Why is “the ease of deployment” considered to be difficult (LOW)  in the case of layered architecture whereas, “the  ease of development criteria” considered to be easy (HIGH) ?
    
2. [ 8 points ]  
    It’s the year 3100. Since the year 2100, mankind has started traveling to distant parts of the universe, resulting in humans spreading in every corner of the nearby galaxies of the Milky Way. People have developed technology to communicate faster than the speed of light. New colonies get created on new planets whereas, in some cases old colonies, along with the planet get destroyed due to natural disasters. When a planet gets destroyed, all the systems on that planet are incapacitated too. To establish a good communication system, humans need a software system that will support these cases. Which architectural pattern will you use? Justify.
### CT 4
An operating system is composed of a bluetooth module, sound system, wifi module and I/O system. These systems don’t have dependencies on each other.  Follow an appropriate software architecture system and draw the diagram demonstrating the above functionalities. 10 points

## Mid
