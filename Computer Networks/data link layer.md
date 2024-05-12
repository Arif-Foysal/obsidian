#networking #link-layer

**Terminologies**
Hosts and routers: **Node**
- communication channels that connect adjacent nodes along communication path: **links**
	- wired
	- wireless
	- LANs
- layer-2 packet: frame, encapsulates datagram.

**Data Link Layer** is the second layer from the bottom in the [[osi model]].

>**link layer has responsibility of transferring datagram from one node to physically adjacent node over a link**

## Link Layer Services
https://www.geeksforgeeks.org/data-link-layer/
### [[Framing]]
encapsulate datagram into frame, adding header, trailer.

### Addressing
[[mac address]] in frame headers identify source, destination (different from [[IP-address]]).

### Link access
Channel access if shared medium.
### Flow control
• pacing between adjacent sending and
receiving nodes
### error detection:
• errors caused by signal attenuation, noise.
• receiver detects errors, signals
retransmission, or drops frame
### error correction:
• receiver identifies and corrects bit error(s)
without retransmission
### Half-duplex and full-duplex:
• with half duplex, nodes at both ends of link
can transmit, but not at same time

## Where is the link layer implemented?
Link layer is generally implemented in the [[network interface card (NIC)]] or sometimes on a chip of each and every host.

- attaches into host’s system buses
- combination of hardware, software, firmware
![[Pasted image 20240511192926.png]]



## Two Types of Links

### Point to point(p2p)
• point-to-point link between Ethernet switch, host
• PPP for dial-up access
### broadcast (shared wire or medium)
• old-fashioned Ethernet
• upstream HFC in cable-based access network
• 802.11 wireless LAN, 4G/4G. satellite
## Multiple Access Protocol

- Single shared broadcast channel. if there is no dedicated link present then multiple stations can access the channel simultaneously. Hence multiple access protocols are required to decrease collision and avoid crosstalk.
**Collision:** If a node receives two or more signals at the same time.
**Interference:** Two or more simultaneous transmissions by nodes.

### But what are multiple access protocol?
**Multiple access protocols** are distributed algorithms that determine how nodes share channel. i.e. Determine when nodes can transmit.
>Communication about channel sharing must use channel itself.

### Classes of MAC protocols

Three broad classes:

**Channel Partitioning:**
- Also known as channelization protocols.
- divide channel into smaller “pieces” (time slots, frequency, code)
- allocate piece to node for exclusive use.
- [[TDMA]], [[FDMA]], [[CDMA]]
<iframe width="560" height="315" src="https://www.youtube.com/embed/HFNbkmub6MQ?si=Cyxgzvmk4E7pxBQ9" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

**Random Access:**
- channel not divided, allow collisions
- **Recover** form collision.
- [[ALOHA]], [[Carrier Sense Multiple Access(CSMA)]]

**Taking Turns:**
- nodes take turns, but nodes with more to send can take longer turns.

### TDMA

![[TDMA]]

### FDMA
![[FDMA]]

### Random Access Protocols
all stations have same superiority that is no station has more priority than another station. Any station can send data depending on medium’s state( idle or busy).

**When node has packet to send:**
- transmit at full channel data rate R.
- no priority coordination among nodes
- two or more transmitting nodes: “collision”
 **random access MAC protocol specifies:**
- how to detect collisions
- how to recover from collisions (e.g., via delayed retransmissions)
- examples of random access MAC protocols:
- ALOHA, slotted ALOHA
- [[Carrier Sense Multiple Access(CSMA)]], CSMA/CD, CSMA/CA

### CSMA 
![[Carrier Sense Multiple Access(CSMA)]]

### Taking Turns MAC Protocols
![[Taking Turns MAC Protocol]]

## MAC Address

![[mac address]]





