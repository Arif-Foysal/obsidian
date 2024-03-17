#computernetworks #networking 

>[!Links]
>[[client-server architecture vs peer to peer architecture]]

![[Client-server-model.svg]]
The **client–server model** is a [distributed application](https://en.wikipedia.org/wiki/Distributed_application "Distributed application") structure that partitions tasks or workloads between the providers of a resource or service, called [servers](https://en.wikipedia.org/wiki/Server_(computing) "Server (computing)"), and service requesters, called [clients](https://en.wikipedia.org/wiki/Client_(computing) "Client (computing)").[](https://en.wikipedia.org/wiki/Client%E2%80%93server_model#cite_note-1)

In client-server architecture:
A [[server]] needs -
- Always on host
- Permanent IP address
- Data centers for scaling
- e.g. [[web server]]
A client -
- May have dynamic IP address
- Do not communicate directly with each other, rather they communicate through a server if they need to communicate.
- May be irregularly connected

Often clients and servers communicate over a [computer network](https://en.wikipedia.org/wiki/Computer_network "Computer network") on separate hardware, but both client and server may reside in the same system (like when you start a web server on your computer and access it through browser of the same computer). A server [host](https://en.wikipedia.org/wiki/Host_(network) "Host (network)") runs one or more server programs, which share their resources with clients. A client usually does not share any of its resources, but it requests content or service from a server. Clients, therefore, initiate communication sessions with servers, which await incoming requests. Examples of computer applications that use the client–server model are [email](https://en.wikipedia.org/wiki/Email "Email"), network printing, and the [World Wide Web](https://en.wikipedia.org/wiki/World_Wide_Web "World Wide Web").

Clients and servers exchange messages in a [request–response](https://en.wikipedia.org/wiki/Request%E2%80%93response "Request–response") [messaging pattern](https://en.wikipedia.org/wiki/Messaging_pattern "Messaging pattern"). The client sends a request, and the server returns a response. This exchange of messages is an example of [inter-process communication](https://en.wikipedia.org/wiki/Inter-process_communication "Inter-process communication"). To communicate, the computers must have a common language, and they must follow rules so that both the client and the server know what to expect. The language and rules of communication are defined in a [[network protocol]]. 

