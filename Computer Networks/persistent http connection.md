#http #networking #protocol 

- [[http]] client initializes [[TCP]] connection to the [[http]] server. Then the server sends acknowledgement, accepting the connection (takes 1 [[Round Trip Time(RTT)]])
- client sends http request(containing url) to the server and server sends a response to that request (takes 1 [[Round Trip Time(RTT)]])
- server leaves the connection **open** so that it can respond to more requests without initializing the connection again.
