#networking 

Demultiplexing in [[transport layer]] is basically using the transport header info to deliver the received segments to correct [[socket]].

> Demultiplexing occurs in receiver end.

## How demultiplexing works

- Host receives [[ip datagram|ip datagrams]]. 
	- Each datagram has source [[IP-address]] and destination [[IP-address]].
	- Each datagram contains one transport layer segment.
	- Each datagram has source, destination port number.
- Host uses [[IP-address]] and [[port]] number to send segment to appropriate [[socket]].
