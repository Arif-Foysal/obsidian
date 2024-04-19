#networking #reliability 

RDT 1.0 works on a **perfectly reliable channel**.

![[reliable channel]]

![[Pasted image 20240419193319.png]]

The [[Finite State machine]] shows the rdt 1.0 sender and receiver.
**The sending side of rdt**
- Accepts data from upper layer via `rdt_send(data)` event.
- Creates packets containing the data via `make_pkt(data)`.
- Sends the packet into the channel using `udt_send(packet)`
**Receiver side of rdt**
- Receives packet from underlying channel via `rdt_rcv(packet)`
- Extracts data from packet using `extract(packet,data)`
- Passes data to upper layer using `deliver_data(data)`
