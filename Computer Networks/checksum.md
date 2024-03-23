#networking 

Checksum error detection is a method used to identify errors in transmitted data. The process involves dividing the data into equally sized segments and using a 1’s complement to calculate the sum of these segments. The calculated sum is then sent along with the data to the receiver. At the receiver’s end, the same process is repeated and if all zeroes are obtained in the sum, it means that the data is correct.

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


