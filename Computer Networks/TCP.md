#networking #protocol 

>[!Links]
>[[difference between tcp and udp]]


### What is TCP?
TCP stands for Transmission Control Protocol, which is a [[transport layer]] protocol. Transmission Control Protocol is a [[connection-oriented protocol]] for communications that helps in the exchange of messages between different devices over a network. The Internet Protocol (IP), which establishes the technique for sending data packets between computers, works with TCP.

### IP
![[IP-address]]

### How does TCP work?
To make sure that each message reaches its target location intact, the TCP/IP model breaks down the data into small bundles and afterward reassembles the bundles into the original message on the opposite end. Sending the information in little bundles of information makes it simpler to maintain efficiency as opposed to sending everything in one go. 

After a particular message is broken down into bundles, these bundles may travel along multiple routes if one route is jammed but the destination remains the same.

![[Pasted image 20240322001512.png]]

**For Example:**
When a user requests a web page on the internet, somewhere in the world, the server processes that request and sends back an HTML Page to that user. The server makes use of a protocol called the HTTP Protocol. The HTTP then requests the TCP layer to set the required connection and send the HTML file.

Now, the TCP breaks the data into small packets and forwards it toward the Internet Protocol (IP) layer. The packets are then sent to the destination through different routes.

The TCP layer in the user’s system waits for the transmission to get finished and acknowledges once all packets have been received.

## Features of TCP/IP

Some of the most prominent features of Transmission control protocol are mentioned below.

- ****Segment Numbering System:**** TCP keeps track of the segments being transmitted or received by assigning numbers to each and every single one of them. A specific Byte Number is assigned to data bytes that are to be transferred while segments are assigned __sequence numbers__. Acknowledgment Numbers are assigned to received segments.
- ****Connection Oriented:**** It means sender and receiver are connected to each other till the completion of the process. The order of the data is maintained i.e. order remains same before and after transmission.
- ****Full Duplex:**** In TCP data can be transmitted from receiver to the sender or vice – versa at the same time. It increases efficiency of data flow between sender and receiver. 
- ****Flow Control:**** Flow control limits the rate at which a sender transfers data. This is done to ensure reliable delivery. The receiver continually hints to the sender on how much data can be received (using a sliding window).
- ****Error Control:**** TCP implements an error control mechanism for reliable data transfer. Error control is byte-oriented. Segments are checked for error detection. Error Control includes – Corrupted Segment & Lost Segment Management, Out-of-order segments, Duplicate segments, etc.
- ****Congestion Control:**** TCP takes into account the level of congestion in the network. Congestion level is determined by the amount of data sent by a sender.

## ****Advantages of TCP****

- It is a reliable protocol.
- It provides an error-checking mechanism as well as one for recovery.
- It gives flow control.
- It makes sure that the data reaches the proper destination in the exact order that it was sent.
- Open Protocol, not owned by any organization or individual.
- It assigns an IP address to each computer on the network and a domain name to each site thus making each device site to be distinguishable over the network.

## ****Disadvantages of TCP****

- TCP is made for Wide Area Networks, thus its size can become an issue for small networks with low resources.
- TCP runs several layers so it can slow down the speed of the network.
- It is not generic in nature. Meaning, it cannot represent any protocol stack other than the TCP/IP suite. E.g., it cannot work with a Bluetooth connection.
- No modifications since their development around 30 years ago.

**ref:** https://www.geeksforgeeks.org/what-is-transmission-control-protocol-tcp/