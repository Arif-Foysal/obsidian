#networking #protocol 

>[!Links]
>- [[connectionless protocol]]
>## Error Checking
>[[checksum]]
>[[Cyclic Redundancy Check(CRC)]]
>- [[reliable and unreliable protocol]]
>- 

User Datagram Protocol(UDP) is a [[transport layer]] protocol. UDP is an unreliable and [[connectionless protocol]]. 
#### What is connectionless protocol anyway?
![[connectionless protocol]]

## Why there is a UDP when we already have TCP/IP?
- no connection establishment(which can add to [[Round Trip Time(RTT)]] delay)
- **simple:** no connection state at sender, receiver
- small header size
- no congestion control
	- UDP can blast away as fast as desired!
	- can function in the face of congestion(which [[tcp-ip model]] kinda struggles with)
- Unlike TCP, the Checksum calculation is **not mandatory** in UDP. Hence UDP depends on [[IP-address|IP]] and [[ICMP]] for error reporting. // - [ ] recheck

For the above reasons, UDP is a better option for real-time services like gaming, voice and video calls, live conferences.
### Differences between TCP and UDP

![[Tcp vs udp]]



### Advantages and Disadvantages of UDP
#### Advantages of UDP

- ****Speed:**** UDP is faster than TCP because it does not have the overhead of establishing a connection and ensuring reliable data delivery.
- Lower latency: Since there is no connection establishment, there is lower latency and faster response time.
- ****Simplicity:**** UDP has a simpler protocol design than TCP, making it easier to implement and manage.
- ****Broadcast support:**** UDP supports broadcasting to multiple recipients, making it useful for applications such as video streaming and online gaming.
- ****Smaller packet size:**** UDP uses smaller packet sizes than [TCP,](https://www.geeksforgeeks.org/tcp-ip-model/) which can reduce network congestion and improve overall network performance.
- User Datagram Protocol (UDP) is more efficient in terms of both latency and bandwidth.

#### Disadvantages of UDP

- ****No reliability:**** UDP does not guarantee delivery of packets or order of delivery, which can lead to missing or duplicate data.
- ****No congestion control:**** UDP does not have congestion control, which means that it can send packets at a rate that can cause network congestion.
- ****No flow control:**** UDP does not have flow control, which means that it can overwhelm the receiver with packets that it cannot handle.
- ****Vulnerable to attacks:**** UDP is vulnerable to denial-of-service attacks, where an attacker can flood a network with UDP packets, overwhelming the network and causing it to crash.
- ****Limited use cases:**** UDP is not suitable for applications that require reliable data delivery, such as email or file transfers, and is better suited for applications that can tolerate some data loss, such as video streaming(loss tolerant but rate sensitive), online gaming, [[DNS]].
### What if reliable transfer is needed over UDP?
- Add necessary reliability at [[application layer]]
- Add congestion control at [[application layer]]

### UDP Sender Actions
- Application layer message is passed to transport layer(UDP).
- Determines UDP segment header file values.
- Creates UDP segment
- Passes segment to IP
### UDP Receiver Actions
- Receives segment from IP
- checks UDP checksum header value
- Extracts application layer message
- [[demultiplexing in transport layer|demultiplexes]] message up to application via socket.
### UDP Segment Header
![[UDP segment header]]

### UDP Checksum
#### What is checksum?
![[checksum]]



#### Practice Problems

![[Pasted image 20240323120220.png]]

