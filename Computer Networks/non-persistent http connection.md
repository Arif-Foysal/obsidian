#networking 

### Non-persistent without parallel connection

- [[http]] client initializes [[TCP]] connection to the [[http]] server. Then the server sends acknowledgement, accepting the connection (takes 1 [[Round Trip Time(RTT)]])
- client sends http request(containing url) to the server and server sends a response to that request (takes 1 [[Round Trip Time(RTT)]])
- Connection **closed**

>At most 1 object can be sent over one TCP connection, to send more, TCP connection needs to be initialized again for each object.

