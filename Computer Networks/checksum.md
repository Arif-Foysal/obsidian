#networking 

>[!Links]
>- [[Cyclic Redundancy Check(CRC)]]
>- 

Checksum error detection is a method used to identify errors in transmitted data. The process involves dividing the data into various segments with equal length and using a 1’s complement to calculate the sum of these segments. The calculated sum is then sent along with the data to the receiver. At the receiver’s end, the same process is repeated and if all zeroes are obtained in the sum, it means that the data is correct.

![](https://media.geeksforgeeks.org/wp-content/uploads/20200909115220/Checksum.png)
### Checksum Operation at Sender Side
==================================================
- Break the original message into ‘k’ number of subunits/segments with ‘n’ bits in each subunit.
- Create the checksum of the message.
	- Sum all the ‘k’ data blocks.
	- **Wraparound** the carry to the sum,(if any).
	- Do the [[1’s Complement]] to the sum to get the checksum.
	- Note that the checksum will also be in ‘n’ bits.
- The checksum is appended to the end of original data unit then transmitted to the receiver.
### Checksum Operation at Receiver Side
=====================================================
- The receiver receives the data + checksum and passes it to checksum checker.
	- Checksum checker divides the data units into various subunits of equal length and adds all these subunits. These subunits also contain checksum as one of the subunits.
	- The resultant bit is then **complemented**. If the completed result is 0, it means the data is error-free. If the result is non-zero, it means the data contains error.
- If there is no error, data is accepted.
- Else, data is corrupted and therefore, the data is rejected.
### Example

If the data unit to be transmitted is `10101001 00111001`, the following procedure is used at Sender site and Receiver site.

#### Sender Site:
```
    1 0 1 0 1 0 0 1   Subunit 1 
    0 0 1 1 1 0 0 1   Subunit 2
————————————————————
    1 1 1 0 0 0 1 0   Sum using 1’s complement
    0 0 0 1 1 1 0 1   Checksum(complement of sum

```
#### Data transmitted to Receiver:
```
 ————————————————————————————————————————————————————
| 1 0 1 0 1 0 0 1  0 0 1 1 1 0 0 1 | 0 0 0 1 1 1 0 1 |
 ————————————————————————————————————————————————————
                Data                      Checksum
```
#### Receiver Site:

```
1 0 1 0 1 0 0 1        subunit 1  
0 0 1 1 1 0 0 1        subunit 2     
0 0 0 1 1 1 0 1        checksum 
1 1 1 1 1 1 1 1        sum

0 0 0 0 0 0 0 0        sum's complement
```

**Result is zero, it means no error**


### Advantage of Checksum
The checksum detects all the errors involving an odd number of bits as well as the error involving an even number of bits.
### Disadvantages
The main problem is that the error goes undetected if one or more bits of a subunit is damaged and the corresponding bit or bits of a subunit are damaged and the corresponding bit or bits of opposite value in second subunit are also damaged. This is because the sum of those columns remains unchanged.
### Internet Checksum: An Example
Example: add two 16-bit integers
```
	1 1 1 0 0 1 1 0 0 1 1 0 0 1 1 0
	1 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1 
------------------------------------
  1 1 0 1 1 1 0 1 1 1 0 1 1 1 0 1 1
  |
  ------------------------------->1   (wraparound the carry)
    1 0 1 1 1 0 1 1 1 0 1 1 1 1 0 0   (sum)
    0 1 0 0 0 1 0 0 0 1 0 0 0 0 1 1   (checksum) sum's complement
```

**Ref:** https://www.geeksforgeeks.org/error-detection-code-checksum/

