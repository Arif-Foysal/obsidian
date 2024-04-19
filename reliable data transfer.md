
#networking #reliability #rdt1 #root 

>[!Links]
>- [[reliable data transfer over a channel with bit errors(rdt 2)]]

![[Pasted image 20240419111810.png]]

This figure illustrates the framework of [[reliable data transfer]]

![[reliable channel]]


![[Pasted image 20240419113104.png]]

It is the responsibility of a reliable data transfer protocol to implement this service of abstraction.
The task is made difficult by the fact that the layer below the reliable data transfer protocol might be unreliable.

For example: A [[reliable and unreliable protocol|reliable protocol]], [[TCP]] is implemented on top of an unreliable protocol, [[IP-address|IP]].

>However, the complexity of reliable protocol is dependent on characteristics of unreliable channel(loss, corruption etc).

So, we must develop sender and receiver side of a reliable protocol considering increasingly complex models of underlying channel.

We may consider,
	- What protocol mechanisms needed when the underlying channel can corrupt or lose entire packet.

One assumption is that, packets will be delivered in order, but some packets possibly being lost.
>That is, the underlying channel will not reorder packets.

>[!Fact]
>Sender and receiver do not know the state of each other (e.g. was the message delivered?) unless communicated via a message.


### Reliable data transfer protocol interfaces
![[Pasted image 20240419115047.png]]

![[Pasted image 20240419115135.png]]

![[reliable data transfer over a perfectly reliable channel(rdt 1)]]

![[reliable data transfer over a channel with bit errors(rdt 2)]]


### Stop and wait operation
![[stop and wait arq]]