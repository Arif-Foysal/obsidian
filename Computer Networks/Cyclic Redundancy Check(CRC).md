#networking #Computer-Science 

>[!Links]
>[[binary division]]
>[[xor gate|xor operation]]
>[[polynomial expression to binary]]


CRC or Cycle Redundancy Check is a method of detecting accidental changes/errors in the communication channel.

CRC uses **Generator Polynomial** which is available in both sender side and receiver side.

> Generator polynomial acts as [[divisor]] while computing CRC


### Polynomial expression to binary
![[polynomial expression to binary]]





**Ref:** https://www.geeksforgeeks.org/modulo-2-binary-division/

### Generating CRC
- A string of k 0’s are appended in [[least significant bit(LSB)|LSB]] to the original message.
 > k = (number of bits in P(x) - 1)
- The new message is divided by the fixed divisor(generator polynomial) using [[binary division]]. The remainder found from the division is the [[Cyclic Redundancy Check(CRC)|CRC]]
- The calculated [[Cyclic Redundancy Check(CRC)CRC]] is appended in [[least significant bit(LSB)|LSB]] to the original message and send it to the receiver.
#### Example
Let’s say,
	Message M(x) = $x^5+x^4+x+1$ = 1 1 0 0 1 1
	Predetermined P(x) = $x^4+x^3+1$ = 1 1 0 0 1

```
                        ———————> (n-1) 0’s appended
1 1 0 0 1 ) 1 1 0 0 1 1 0 0 0 0 ( 1 0 0 0 0 1
			1 1 0 0 1
			————————————————————
			  0 0 0 0 1
			  0 0 0 0 0
			  ——————————————————
			    0 0 0 1 0
			    0 0 0 0 0
			————————————————————
				  0 0 1 0 0
				  0 0 0 0 0
			—————————————————————
				    0 1 0 0 0
				    0 0 0 0 0
			—————————————————————
					  1 0 0 0 0
					  1 1 0 0 1
			—————————————————————
					    1 0 0 1 ——->(remainder)

```
Therefore, the encoded message to be sent,
`1 1 0 0 1 1 0 0 1`

**Receiver side operation:**
```
						———————> CRC code appended
1 1 0 0 1 ) 1 1 0 0 1 1 1 0 0 1 ( 1 0 0 0 0 1
			1 1 0 0 1
			—————————————————————
			  0 0 0 0 1
			  0 0 0 0 0
			  ———————————————————
			    0 0 0 1 1
			    0 0 0 0 0
			    —————————————————
			      0 0 1 1 0
			      0 0 0 0 0
			      ———————————————
			        0 1 1 0 0
			        0 0 0 0 0 
			        —————————————
			          1 1 0 0 1
			          1 1 0 0 1
			          ——————————
			          0 0 0 0 0 ————> no remainder
```
There is no remainder. So the data has no error.
Therefore, data is accepted!!!


