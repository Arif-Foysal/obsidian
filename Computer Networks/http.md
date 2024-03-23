#networking 

- [ ] Finish this including maths #todo 

>[!Links]
>- [[Round Trip Time(RTT)]]
>- [[TCP 3-way handshake]]
>- [[http message]]
>- [[persistent http connection]]
>- [[non-persistent http connection]]
>- [[http#Packet Delays]]

The Hypertext Transfer Protocol (HTTP) is an application-level protocol that uses TCP as an underlying transport and typically runs on port 80. HTTP is a stateless protocol i.e. server maintains no information about past client requests.
## Round trip time (RTT)

![[Round Trip Time(RTT)]]

## TCP 3-way handshake

![[TCP 3-way handshake]]


### Types of http connections

1. [[persistent http connection]]
2. [[non-persistent http connection]]



![[persistent http connection]]

![[non-persistent http connection]]

### Packet Delays Practice Problems
#practiceProblems

#### Exercise 01:
**Questions :** Assume that you have base HTML file with 30 embedded images, images & base file are small enough
to fit in one TCP segment. How many RTT are required to retrieve base file & images under-following condition :
(i) Non-Persistent connection without parallel connection
(ii) Non-persistent connection with 10 parallel connection
(iii) Persistent connection without pipe-lining
(iv) Persistent connection with pipe-lining
(Assume RTT dominates all other time)
Explanation :
2RTT is the initial required connection one for TCP connection and one for HTML base file.
Total time = 2RTT + transmit time
(i) Non-Persistent connection with no parallel connection :
Here for each image 2 RTT are required one for TCP connection and one for image to send.
So transmit time for 30 images = 2*(30 RTT) = 60 RTT
Total time = 2 RTT+60 RTT = 62RTT
(ii) Non-persistent connection with 10 parallel connection :
Here 10 images can be send simultaneously.
So for 30 images it required -> 2*(30/10) = 6RTT
Total time = 2 RTT + 6 RTT = 8RTT
(iii) Persistent connection without pipelining :
Here TCP connection is required again and again.
So for 30 images it requires -> 30 RTTs
Total time = 2 RTT + 30 RTT = 32RTT
(iv) Persistent connection with pipe-lining :
Since it is Persistent connection TCP connection is not required again and again.
Pipe-lining means in one packet only images which can fit, can be send.
In Pipe-lining connection we can send all images in 1RTT.
Total time = 2 RTT + 1 RTT = 3RTT

#### Exercise 02:

> Suppose a client(web browser) requests an html file which contains 8 .jpg images and 2 .mov video files. Assuming each file fits into 1 TCP segment, how many requests will be sent by the browser?
> Which one of-
> 1. Non persistent
> 2. Persistent
> HTTP will take less time to transfer files. Why?

Total files to be requested,
	1(base html) + 8(jpg) + 2(mov)
	= 11 files

Since each file fits into 1 TCP segment, so number of TCP objects= 11
Therefore, number of requests = 11

Time to transfer files:
	**Non-persistent:**
	2RTT (base html) + (10 x 2)RTT (8 images & 2 videos) + File transfer time
	= 22RTT + file transfer time
	**Persistent:**
	1RTT(initialize) + 11RTT (base file and 10 media files) + file transfer time
	= 12RTT + file transfer time

#### Exercise 03:

>We would like to download an article on the web. This involves two steps:
>Step 1: Download the master index of size B. This page contains links to 4 images. 
>Step 2: Download the 4 images. Each image is also of size B.
>**Assumptions:**
>- Ignore transmission delays
>- Assume HTTP responses fit into a single TCP packet.
>- We dont need to wait for the HTTP responses to be acknowledged nor for the TCP connections to terminate.
>**Calculate time taken to download the article under each of the following scenarios:**
>a) All files are stored at a single origin server S. Use **sequential requests** with **non-persistent** TCP connections.
>
>b) All files are stored at a single origin server S. Use **sequential requests** with **persistent** TCP connectins.
>
>c) All files are stored at a single origin server S. Use **concurrent requests** with **non-persistent** TCP connections.
>
>d) The content provider signs up for a **content delivery network(CDN)** for the delivery of it's images. The master index file is still served from the origin server with 1RTT. Our RTT with closest **CDN** server is (RTT/2). Use **sequential requests** with **non-persistent** TCP connection.
>g) The **CDN** tries to do some [[load balancing]] and different images are served by different CDN servers at distances **3RTT/4, RTT/2, RTT/3, RTT/4**. The master index is still served from the original server. We use **sequential requests** with **non-persistent** TCP connection.
>h) Repeat (g) with **sequential** and **persistent** connection.
>i) Repeat (g) with **concurrent** and **non-persistent** connection.
 
##### Answer
a) 
	Number of requests = 5
	Delay= (5 x 2)RTT
		= 10RTT
b)
	Number of requests = 5
	Delay= 1RTT + 5RTT
		= 6RTT

c)
	Since number of concurrent connections are not given, we assume that,
	number of concurrent connections = number of requests
	So,
	Delay = 2RTT (master index) + 2RTT (4 files)
	**Note:**
	- Master index needs to be downloaded first to get the links of the 4 files. So, to download master index,
		init connection(1RTT) + download master index {req + response} (1RTT)
	- Connection closed
	- Init connection again (1RTT)
	- Request 4 files simultaneously and get responses simultaneously (1RTT)
	- Total = 4RTT

d) 
	Delay = 2RTT (base) + 4(2x(RTT/2)) (4 files) = 6RTT
	**Note:** 
		for 1 image from the **cdn** = 2 x (RTT/2)
		for 4 images from **cdn**    = 4(2 x (RTT/2))
g)
	Delay = 2RTT + 2(3RTT/4) + 2(RTT/2) + 2(RTT/3) + 2(RTT/4)
h) 
	Same as (g), cause the files are not in the same server. The client has to init connection with all the servers anyway, so delay is the same as non-persistent requests.
i) 
	Delay = 2RTT + 2(3/4)RTT
	**Note:** 2RTT for base file(compulsary) + max(each server RTT)



 