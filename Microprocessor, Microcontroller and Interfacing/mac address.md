#networking  #Computer-Science 
## What is a mac address?
**A MAC address, or Media Access Control address, is a unique identifier assigned to a network interface controller (NIC) for use as a network address in communications within a network segment(locally).** This use is common in most IEEE 802 networking technologies, including Ethernet, Wi-Fi, and Bluetooth.
## How to denote mac address?

**each interface on LAN**
- **has unique 48-bit MAC address**

MAC addresses are typically written as a sequence of six groups of two hexadecimal digits, separated by colons, hyphens, or without a separator.

For example,  `00-00-5E-00-53-AF` is a valid MAC address.
## Who assigns mac addresses?
MAC addresses are assigned by device manufacturers, and are therefore often referred to as the burned-in address, or as an Ethernet hardware address, hardware address, or physical address.

- **48-bit MAC address (for most LANs) burned in [[network interface card (NIC)]] ROM, also sometimes software settable.****

## Which layer do mac address used on?
MAC addresses are used at the [[data link layer]] of the OSI model to identify devices on a local network. When a device wants to communicate with another device on the same network, it broadcasts a data frame with the destination device's MAC address in the header. The destination device then responds to the data frame.

MAC addresses can also be used to filter network traffic. For example, a router can be configured to only allow devices with certain MAC addresses to access the internet.

## Here are some examples of how MAC addresses are used:

- To connect to a Wi-Fi network, your device needs to know the MAC address of the Wi-Fi router.
- When you send a file to another computer on the same network, the MAC addresses of both computers are used to ensure that the file is delivered correctly.
- Network administrators can use MAC addresses to troubleshoot network problems and to control access to the network.





## MAC Addresses
each interface on LAN 
- has unique 48-bit MAC address 
- has a locally unique 32-bit [[IP-address]] (as we’ve seen)

## How to determine interface's MAC Address knowing it's IP-address?
Using [[ARP Table]].
### ARP Table
Each ip node(host, router) on LAN has this table. 
This table holds IP/MAC address mapping.

IP/MAC address mapping for some LAN node(basically a row in the ARP table):
`<IP address; MAC address; TTL>`

[[Time To Leave(TTL)]]: Time after which address mapping will be forgotten.(typically 20 minutes)

### ARP Protocol in action

>**Let's say A wants to send Datagram to B. But B's MAC Address is not on A's ARP Table.**

A uses ARP query to find B's MAC Address.

**Step 1:** A broadcasts ARP query, containing B's IP address.

- [ ] verify later #todo 
	Broadcast MAC Address is probably `FF-FF-FF-FF-FF-FF`

![[Pasted image 20240512124443.png]]

**Step 2:** B replies to A with ARP response, giving its MAC address.

![[Pasted image 20240512124759.png]]

**Step 3:** A receives B’s reply, adds B entry into its local ARP table.

![[Pasted image 20240512125504.png]]


### Routing to another subnet: Addressing
