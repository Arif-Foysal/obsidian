#networking 

Also known as delayed ack.

Occurs when packet is received, but ack is delayed. In this case, 
- sender is going to retransmit the packet after timeout
- Receiver will detect duplicate, ignore the packet(since already received before), send ack of the packet.
- Sender will accept one ack of the packet, and ignore ack of the same packet onwards.
![[Pasted image 20240419224727.png]]

