#robotics #drone #quadRotor

>[!Links]
>[[autonomous flight]]
>[[degrees of freedom]]


Quad-rotors consists of 4 independently controlled rotors, mounted in a rigid frame.

### Controlling position and orientation of a quad rotor

![[IMG_0706 1.png]]

The position and orientation of a quad-rotor can be controlled by varying the speeds of the independent motors.

### Roll and pitch

![[IMG_0707.jpeg]]

If you rotate one rotor faster than the other, it will cause the robot to pitch in one direction. 

### Yaw motion 
If you wanna move the vehicle from one side to another, translating it along the [[horizontal]] direction,
Let’s just say you want to go from point x to point y.
![[IMG_0709.jpeg]]

- Pitch the robot forward, so that the [[thrust vector]] points the horizontal direction. This allows the vehicle to accelerate forward.
	![[IMG_0711.jpeg]]
	![[IMG_0712.jpeg]]
- When you get close to the destination, you want to stop the vehicle, for that you have to pitch it in the opposite direction, creating a reverse thrust resulting the robot to slow down as it approaches the destination.
	![[IMG_0713.jpeg]]
- Pitch the robot back to equilibrium.
	![[IMG_0714.jpeg]]