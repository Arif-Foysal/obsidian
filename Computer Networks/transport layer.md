#networking #Computer-Science 
>[!Links]
>## Multiplexing/Demultiplexing
>[[multiplexing in transport layer]]
>[[demultiplexing in transport layer]]
>## Transport layer protocols
>[[TCP]]
>[[UDP]]
>## Error Detection
>[[Checksum]]
>[[Cyclic Redundancy Check(CRC)]]



Transport layer provides logical communication between application processes running on different hosts. Transport layer is the second layer in [[tcp-ip model]] and fourth layer in the [[osi model]]. 
## The job of transport layer
Transport layer,
- Provides service to the [[network layer]]
- Takes service from the [[application layer]]
### At the senders side
The transport layer receives data(message) from application layer and then performs segmentation, **divides the actual message** into segments, adds the **source** and **destination’s port numbers** into the **header** of the segment, and transfers the message to the [[network layer]].

### At the receivers side
The transport layer receives data from the Network layer, reassembles the segmented data, reads its header, identifies the port number, and delivers the message to the appropriate port in the Application layer.
![[process communication#How to uniquely identify a process on a network]]

## Responsibilities of transport layer
- Process to process delivery
- End to end connection between hosts
- [[multiplexing in transport layer|multiplexing]] and [[demultiplexing in transport layer|demultiplexing]]
- Congestion control
- Data integrity and error correction
- Flow control

### Multiplexing
![[multiplexing in transport layer]]

### Demultiplexing
















