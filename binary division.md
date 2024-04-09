Also known as **modulo 2 binary division**.
The division process is kinda the same as decimal [[division]].

### Steps
- In each step, a copy of the [[divisor]] is [[xor gate|xor]]ed with the n bits of the [[dividend]] and take 1 in [[quotient]].
  >n = # of bits in divisor
- The result of xor operation(remainder) is used for next step. 1 bit from [[dividend]] is pulled down to make the remainder n bits long. If still not divisible by dividend, we xor it by n # of 0’s and take 0 in [[quotient]]
- Repeat until there are no bits to pull down. We have the final remainder now. It should be n-1 bits long.

### Example
```
1 1 0 1 ) 1 0 0 1 0 0 0 0 0 ( 1 1 1 1 0 1 —> Quotient
          1 1 0 1
          ————————————————
            1 0 0 0
            1 1 0 1
        ——————————————————
              1 0 1 0
              1 1 0 1
        ——————————————————
		        1 1 1 0
		        1 1 0 1
		——————————————————
				  0 1 1 0
				  0 0 0 0
		——————————————————
					1 1 0 0
					1 1 0 1
			——————————————————
					  0 0 1 ——> Remainder
```

