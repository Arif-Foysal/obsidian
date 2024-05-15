#networking 

## Network Layer Functions
### Forwarding
Moving packets from a router's input link to appropriate output link.
- Process of getting through a single interchange
### Routing 
Determining route taken by packets from source to
destination.
- Process of planning trip from source to destination.

## DHCP
A protocol that allows a host to obtain [[IP-address]] automatically. 
A network administrator can configure DHCP so that a given host receives the same IP address each time it connects to the network, or a host may be assigned a temporary IP address that will be different each time the host connects to the network.
### Steps for a newly arriving host
**Step 1: DHCP server discovery.**
• A newly arriving host is to find a DHCP server with which to interact using a DHCP discover message
• A client sends within a UDP packet to port 67. The UDP packet is encapsulated in an IP datagram.
• But to whom should this datagram be sent?
• DHCP discover message along with the broadcast destination IP address of 255.255.255.255 and a “this host” source IP address of 0.0.0.0.
**Step 2: DHCP server offer(s).**
• A DHCP server receiving a DHCP discover message responds to the client with a DHCP offer message using the IP broadcast address of 255.255.255.255.
• Why this server reply must also be broadcast ?
• Since several DHCP servers can be present on the subnet.
**Step 3: DHCP request.**
• The newly arriving client will choose from among one or more server offers and
• Respond to its selected offer with a DHCP request message, echoing back the configuration parameters.
**Step 4: DHCP ACK.**
• The server responds to the DHCP request message with a DHCP ACK message, confirming the requested parameters.

![[Pasted image 20240514223503.png]]

## Network Address Translation(NAT)
NAT (Network Address Translation) is a technique for preserving scarce Internet IP addresses.

It converts private IP addresses (not routable to Internet) to public IP addresses so that Internet can be accessed from private network.

**advantages:**
 just one IP address needed from provider ISP for all devices
 can change addresses of host in local network without notifying outside world
 can change ISP without changing addresses of devices in local network
 security: devices inside local net not directly addressable, visible by outside world


**implementation: NAT router must (transparently):**
 outgoing datagrams: replace (source IP address, port #) of every outgoing datagram to (NAT IP address, new port #)
• remote clients/servers will respond using (NAT IP address, new port #) as destination address
 remember (in NAT translation table) every (source IP address, port #) to (NAT IP address, new port #) translation pair
 incoming datagrams: replace (NAT IP address, new port #) in
destination fields of every incoming datagram with corresponding (source IP address, port #) stored in NAT table

![[Pasted image 20240514230826.png]]

![[Pasted image 20240514230848.png]]


## IP Fragmentation
Network links often have MTU(Max Transferrable Unit)
So, any datagram larger than MTU is divided into sub units.
![[Pasted image 20240515083634.png]]
![[Pasted image 20240515083724.png]]

## IPv4
The limitations of [[ipv4]]:
• IPv4 address depletion – We have basically run out of IPv4 addressing.
• Lack of end-to-end connectivity – To make IPv4 survive this long, private addressing and NAT were created. This ended direct communications with public addressing.
• Increased network complexity – NAT was meant as temporary solution and creates issues on the network as a side effect of manipulating the network headers addressing. NAT causes latency and troubleshooting issues.

### IPv4 Addressing
IPv6 addresses are 128 bits in length and written in hexadecimal.

IPv6 addresses are not case-sensitive and can be written in either lowercase or uppercase.

The preferred format for writing an IPv6 address is x:x:x:x:x:x:x:x, with each “x” consisting of four hexadecimal values.

In IPv6, a hextet is the unofficial term used to refer to a segment of 16 bits, or four hexadecimal values.

#### Rule 1: Omit leading 0's
![[Pasted image 20240515085058.png]]

#### Rule 2: Double colon
Note: The double colon (::) can only be used once within an address, otherwise there would be more than one possible resulting address.

![[Pasted image 20240515085156.png]]


## IPv4 and IPv6 Coexistence
Both IPv4 and IPv6 will coexist in the near future and the transition will take several years.

**IPv4 and IPv6 can co-exist together using the following techniques:**
• **Dual stack** -The devices run both IPv4 and IPv6 protocol stacks simultaneously.
• **Tunneling** – A method of transporting an IPv6 packet over an IPv4 network. The IPv6 packet is encapsulated inside an IPv4 packet.
• **Translation** - Network Address Translation 64 (NAT64) allows IPv6-enabled devices to communicate with IPv4-enabled devices using a translation technique similar to NAT for IPv4.

### Tunneling
IPv6 datagram carried as payload in IPv4 datagram among
IPv4 router.

![[Pasted image 20240515085932.png]]

![[Dijkstra's Algorithm]]
