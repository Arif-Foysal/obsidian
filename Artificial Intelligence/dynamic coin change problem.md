#Algorithm #dynamicProgramming 

**Problems:**
- Total number of ways the change can be made.
	- Print the coins.
- Minimum number of coins needed to make the change.
	- Print the coins.
### Approach
**Given,**
Coins = {1, 3, 5}
W = 8 

Here, j ranges from 0 to amount needed to be changed
i = given coins
`k[i][j]` represents minimum coins required to change amount `[j]` with coin denominations `[i]=0 to [i]`

**How to fill `K[i][j]`**
```
If(k[j] < k[i]):
	k[i][j] = k[i-1][j]
Else:
	//Calculate number of ways
	k[i][j] = (k[i-1][j]) + 
```


```
Coin(i) `\` amount(j) ->
⇣
```

| **coins\amount** | 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   |
| ---------------: | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|                0 | 0   | inf | inf | inf | inf | inf | inf | inf | inf |
|                1 | 0   |     |     |     |     |     |     |     |     |
|                3 | 0   |     |     |     |     |     |     |     |     |
|                5 | 0   |     |     |     |     |     |     |     |     |
|                  |     |     |     |     |     |     |     |     |     |


```
0 2147483647 2147483647 2147483647 2147483647 2147483647 2147483647 2147483647 2147483647 
0 1 2 3 4 5 6 7 8 
0 1 2 1 2 3 2 3 4 
0 1 2 1 2 1 2 3 2 
```

### Pseudo-code
```pseudocode
function minCoins(coins[], amount):
	n = coins.length
	// Create a 2D array to store results of subproblems
	dp[][] = new Array(n+1, amount+1)
	// Initialize the base cases
	for i from 0 to n:
		dp[i][0] = 0
	for j from 0 to amount:
		dp[0][j] = infinity
	// Fill the dp table
	for i from 1 to n:
	for j from 1 to amount:
	// If the current coin denomination is greater than the current amount, we cannot include it, so copy the previous row's value
	if coins[i-1] > j:
	dp[i][j] = dp[i-1][j]
	else:
	// Otherwise, take the minimum of (not using current coin, 1 + using current coin)
	dp[i][j] = min(dp[i-1][j], 1 + dp[i][j - coins[i-1]])
	return dp[n][amount]
```

 