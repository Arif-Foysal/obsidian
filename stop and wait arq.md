#networking 

#### Sender:
Rule 1. Send one data packet at a time.   
Rule 2. Send the next packet only after receiving acknowledgement for the previous. That is, the rdt_send() event occurs after the sender receives an ACK.   
#### Receiver:
Rule 1. Send acknowledgement after receiving and consuming a data packet.   
Rule 2. After consuming packet acknowledgement need to be sent ([[Flow Control]])

protocols in [[reliable data transfer over a channel with bit errors(rdt 2)]] are known as stop and wait protocols.

### Reliability in stop and wait

- The sender does not know whether a data packet was lost, an ACK was lost, or if the packet or ACK was simply overly delayed.
	- In all cases, the action is the same: retransmit.
- Time-based retransmission mechanism requires a countdown timer.
- The sender will need to 
	- (1) start the timer each time a packet is sent
	- (2) respond to a timer interrupt
	- (3) stop the timer.
![[Pasted image 20240419223834.png]]

- packet sequence number alter between 0 and 1. Protocol rdt 3.0 is known as altering bit protocol.
![[Pasted image 20240419224226.png]]
**Figure**: [[ack loss]] and [[premature timeout]]

### Performance impact on stop and wait
[[packet delay and loss]]
![[Pasted image 20240515114013.png]]

### Characteristics

- Used in Connection-oriented communication.
- It offers error and flows control
- It is used in Data Link and Transport Layers
- Stop and Wait for ARQ mainly implements the Sliding Window Protocol concept with Window Size 1

### Useful Terms:

- **Propagation Delay:** Amount of time taken by a packet to make a physical journey from one router to another router.

Propagation Delay = (Distance between routers) / (Velocity of propagation)

- RoundTripTime (**RTT**) = Amount of time taken by a packet to reach the receiver + Time taken by the Acknowledgement to reach the sender 
- TimeOut (**TO**) =  2* RTT
- Time To Live (**TTL**) = 2* TimeOut. (Maximum TTL is 255 seconds)
[[Transmission delay]] = L/R 
					= (size of packet e.g. 4 bytes) / (transmission rate e.g. 2bps)
- [ ] verify this #todo 

## Pipelined protocol operations using stop and wait


![[Pasted image 20240419232251.png]]

If the sender is allowed to transmit 03 packets before having to wait for acknowledgments, the utilization of the sender is essentially tripled.
Since the many in-transit sender-to-receiver packets can be visualized as filling a pipeline, this technique is known as pipelining.

## Go-Back-N in action – Pipeline Protocol
In a Go-Back-N (GBN) protocol, the sender is allowed to transmit multiple packets (when available) without waiting for an acknowledgment, but is constrained to have no more than some maximum allowable number, N, of unacknowledged packets in the pipeline.
![[Pasted image 20240419232600.png]]

### Flaws of go-back-n in action
When the window size and bandwidth-delay product are both large, many packets can be in the pipeline. **A single packet error can thus cause GBN to retransmit a large number of packets, many unnecessarily**.

To overcome this, selective repeat in action comes in.

## Selective repeat in action

![[Pasted image 20240419233355.png]]


**ref:** https://www.geeksforgeeks.org/stop-and-wait-arq/