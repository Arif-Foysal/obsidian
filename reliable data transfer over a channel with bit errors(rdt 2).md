#networking #reliability #rdt2 #root

When the underlying channel is not [[reliable channel]].
That is,
- bits in packets may be corrupted
- packets may not deliver in order to which they were sent.

Such bit errors typically occur in physical components of network([[physical layer]]) as packets are propagated/transmitted.

[[reliable and unreliable protocol|reliable protocols]] are based on [[automatic repeat request(arq) protocol]].

![[automatic repeat request(arq) protocol]]

### Sending side

![[Pasted image 20240419220246.png]]
In one state, the send-side protocol is waiting for data to be passed down from the upper layer to lower layer.

In the other state, the sender protocol is waiting for an ACK or a NAK packet from the receiver( a feedback). 

**If an ACK packet is received** i.e rdt_rcv(rcvpkt) && is ACK(rcvpkt), the sender knows that the most recently transmitted packet has been received correctly and thus the protocol returns to the state of waiting for data from the upper layer. 

**If a NAK is received**, the protocol re-transmits the last packet and waits for an ACK or NAK to be returned by the receiver in response to the re-transmitted data packet.

### Receiving Side
![[Pasted image 20240419221642.png]]

The receiver-site has a single state, as soon as the packet arrives, the receiver replies with either an ACK or a NAK, depending on whether or not the received packet is corrupted i.e. by using rdt_rcv(rcvpkt) && corrupt(rcvpkt) where a packet is received and is found to be in error or rdt_rcv(rcvpkt) && not corrupt(rcvpkt) where a packet received is correct.


![[flaws of rdt 2]]




**Learn more:** https://www.geeksforgeeks.org/reliable-data-transfer-rdt-2-0/?ref=ml_lbp
