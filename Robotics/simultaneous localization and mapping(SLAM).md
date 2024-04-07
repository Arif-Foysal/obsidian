#robotics #autonomous 

>[!Links]
>- [[autonomous navigation]]
>- 



### What is SLAM?
Simultaneous Localization and Mapping(SLAM) is a method that allows [[autonomous vehicles]] and robots to build a map and localize itself on the map at the same time. 

Using wide range of [[algorithms]], computations and sensory data, SLAM software system allows an agent to map out unfamiliar environment while simultaneously identifying it’s own location within that environment.

### An example of SLAM application
Let’s consider a robot vacuum. Without SLAM, it will just move randomly within the room and may not be able to clean the entire surface of the room. 
On the other hand, robots with SLAM algorithm can use information such as **number of wheel revolutions, data from cameras and other sensors** to determine the amount of movement needed(localization). The robot can also create map of the obstacles in it’s surroundings and avoid cleaning the same area twice(mapping).

SLAM algorithms are useful in many other applications such as-
- parking a self-driving car.
- Delivering a package by navigating a drone in an unknown environment.

[[matlab]] and [[simulink]] provide various kinds of [[SLAM algorithms]], functions and analysis tools to develop various applications.

SLAM can also be implemented with other tasks such as object tracking, path planning, path following and so on.

**Ref:** 
1. https://www.mathworks.com/discovery/slam.html
2. https://www.flyability.com/simultaneous-localization-and-mapping
