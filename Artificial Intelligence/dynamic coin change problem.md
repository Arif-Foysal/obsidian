#Algorithm #dynamicProgramming 

**Problems:**
- Total number of ways the change can be made.
	- Print the coins.
- Minimum number of coins needed to make the change.
	- Print the coins.

Coins = {2, 3, 5, 10}
W = 15

### Approach


Here, j ranges from 0 to amount needed to be changed
i = given coins
`k[i][j]` represents how many ways there can be to change amount `[j]` with coin `[i]`

**How to fill `K[i][j]`**
```
If(k[j] < k[i]):
	k[i][j] = k[i-1][j]
Else:
	//Calculate number of ways
	k[i][j] = (k[i-1][j]) + 
```

Coin(i) `\` amount(j) ->
⇣

| coin\amount | 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | 11  | 12  | 13  | 14  | 15  |
| ----------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 2           | 1   | 0   | 1   | 0   | 1   | 0   | 1   | 0   | 1   | 0   | 1   | 0   | 1   | 0   | 1   | 0   |
| 3           | 1   | 0   | 0   | 1   |     |     |     |     |     |     |     |     |     |     |     |     |
| 5           | 1   |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |
| 10          | 1   |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |
|             |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |


