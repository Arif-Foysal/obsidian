#networking 

Switch is a link-layer device: takes an active role
- store, [[forwarding|forward]] Ethernet frames.
- examine incoming frame’s MAC address, selectively forward frame to one-or-more outgoing links when frame is to be forwarded on segment, uses [[Carrier Sense Multiple Access(CSMA)|CSMA]]/CD to access segment.
- transparent: hosts unaware of presence of switches
- plug-and-play, self-learning
- switches do not need to be configured

### Self-Learning property of switch:
Switches are known to have so called **self-learning** properties. That is, **switch table** is built automatically, dynamically and autonomously without any intervention from a network administrator or from any configuration protocol.

This capability is accomplished by as follows:
- The switch table is initially empty.
- For each incoming frame received on interface, the switch stores following information in it's table:
	- The [[mac address]] in the frame's source address field.
	- The interface from which the frame arrived
	- The current time.
This way the switch records the **LAN segment on which the sender resides** on it's table. If every host sends a frame, then every hosts will get recorded on the table. 

As a result, **switch learns which hosts can be reached through**
**which interfaces**.

>The switch deletes an entry from the table after a certain time([[Time To Leave(TTL)]]) of inactivity of that interface.

![[Pasted image 20240512132912.png]]


If interface of the frame destination is known(is on the table): **send to that particular link/interface**
If interface of the frame destination is unknown(not found on the table): **flood**
### Switch Forwarding Table
Used to store information about which node is connected to which interface of the switch.
