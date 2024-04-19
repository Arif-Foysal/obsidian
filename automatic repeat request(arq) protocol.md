#networking 

Additional protocol capabilities are required in arq to handle presence of bit errors:
- Error detection 
	- [[checksum]]
	- [[Cyclic Redundancy Check(CRC)]]
- Receiver feedback:
	- positive(ACK) acknowledgments
(“OK”)
	- negative(NACK) acknowledgments(nack)
(“Please repeat that.”)	
- Retransmission

![[stop and wait arq]]