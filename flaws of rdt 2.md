#networking 

RDT 2.0 may look as if it works but it has some has some flaws.

- It is difficult to understand whether the bits to ACK/NAK packets are actually corrupted or not.
	- if the packet is corrupted how protocol will recover from this errors in ACK or NAK packets. The difficulty here is that if an ACK or NAK is corrupted, the sender has no way of knowing whether or not the receiver has correctly received the last piece of transmitted data or not.