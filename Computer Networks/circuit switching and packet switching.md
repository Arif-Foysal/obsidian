#networking 
### What is Circuit Switching?

Circuit switching is a communication method where a dedicated communication path, or circuit, is established between two devices before data transmission begins. The circuit remains dedicated to the communication for the duration of the session, and no other devices can use it while the session is in progress. Circuit switching is commonly used in voice communication and some types of data communication.

_**Advantages of Circuit Switching:**_

- Guaranteed bandwidth: Circuit switching provides a dedicated path for communication, ensuring that bandwidth is guaranteed for the duration of the call.
- Low latency: Circuit switching provides low latency because the path is predetermined, and there is no need to establish a connection for each packet.
- Predictable performance: Circuit switching provides predictable performance because the bandwidth is reserved, and there is no competition for resources.
- Suitable for real-time communication: Circuit switching is suitable for real-time communication, such as voice and video, because it provides low latency and predictable performance.

_**Disadvantages of Circuit Switching:**_

- Inefficient use of bandwidth: Circuit switching is inefficient because the bandwidth is reserved for the entire duration of the call, even when no data is being transmitted.
- Limited scalability: Circuit switching is limited in its scalability because the number of circuits that can be established is finite, which can limit the number of simultaneous calls that can be made.
- High cost: Circuit switching is expensive because it requires dedicated resources, such as hardware and bandwidth, for the duration of the call.

### What is Packet Switching?

Packet switching is a communication method where data is divided into smaller units called packets and transmitted over the network. Each packet contains the source and destination addresses, as well as other information needed for routing. The packets may take different paths to reach their destination, and they may be transmitted out of order or delayed due to network congestion.

_**Advantages of Packet Switching:**_

- Efficient use of bandwidth: Packet switching is efficient because bandwidth is shared among multiple users, and resources are allocated only when data needs to be transmitted.
- Flexible: Packet switching is flexible and can handle a wide range of data rates and packet sizes.
- Scalable: Packet switching is highly scalable and can handle large amounts of traffic on a network.
- Lower cost: Packet switching is less expensive than circuit switching because resources are shared among multiple users.

_**Disadvantages of Packet Switching:**_

- Higher latency: Packet switching has higher latency than circuit switching because packets must be routed through multiple nodes, which can cause delay.
- Limited QoS: Packet switching provides limited QoS guarantees, meaning that different types of traffic may be treated equally.
- Packet loss: Packet switching can result in packet loss due to congestion on the network or errors in transmission.
- Unsuitable for real-time communication: Packet switching is not suitable for real-time communication, such as voice and video, because of the potential for latency and packet loss.

###  Similarities:

- Both methods involve the transmission of data over a network.
- Both methods use a physical layer of the OSI model for transmission of data.
- Both methods can be used to transmit voice, video, and data.
- Both methods can be used in the same network infrastructure.
- Both methods can be used for both wired and wireless networks.

### Difference between Circuit Switching and Packet Switching:

|**Circuit Switching**|**Packet Switching**|
|---|---|
|In-circuit switching has there are 3 phases:   <br>i) Connection Establishment.   <br>ii) Data Transfer.   <br>iii) Connection Released.|In Packet switching directly data transfer takes place.|
|In-circuit switching, each data unit knows the entire path address which is provided by the source.|In Packet switching, each data unit just knows the final destination address intermediate path is decided by the routers.|
|In-Circuit switching, data is processed at the source system only|In Packet switching, data is processed at all intermediate nodes including the source system.|
|The delay between data units in circuit switching is uniform.|The delay between data units in packet switching is not uniform.|
|Resource reservation is the feature of circuit switching because the path is fixed for data transmission.|There is no resource reservation because bandwidth is shared among users.|
|Circuit switching is more reliable.|Packet switching is less reliable.|
|Wastage of resources is more in Circuit Switching|Less wastage of resources as compared to Circuit Switching|
|It is not a store and forward technique.|It is a store and forward technique.|
|Transmission of the data is done by the source.|Transmission of the data is done not only by the source but also by the intermediate routers.|
|Congestion can occur during the connection establishment phase because there might be a case where a request is being made for a channel but the channel is already occupied.|Congestion can occur during the data transfer phase, a large number of packets comes in no time.|
|Circuit switching is not convenient for handling bilateral traffic.|Packet switching is suitable for handling bilateral traffic.|
|In-Circuit switching, the charge depends on time and distance, not on traffic in the network.|In Packet switching, the charge is based on the number of bytes and connection time.|
|Recording of packets is never possible in circuit switching.|Recording of packets is possible in packet switching.|
|In-Circuit Switching there is a physical path between the source and the destination|In Packet Switching there is no physical path between the source and the destination|
|Circuit Switching does not support store and forward transmission|Packet Switching supports store and forward transmission|
|Call setup is required in circuit switching.|No call setup is required in packet switching.|
|In-circuit switching each packet follows the same route.|In packet switching packets can follow any route.|
|The circuit switching network is implemented at the physical layer.|Packet switching is implemented at the datalink layer and network layer|
|Circuit switching requires simple protocols for delivery.|Packet switching requires complex protocols for delivery.|