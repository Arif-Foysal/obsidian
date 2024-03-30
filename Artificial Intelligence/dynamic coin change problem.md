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
	//Calculate minimum number of coins between taking the coin and not taking the coin.
	k[i][j] = min(k[i-1][j]), 1 + k[i][j - coins[i-1] ])
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
### Code

```cpp
#include <iostream>
#include <vector>
#include <climits>

using namespace std;

int minCoins(vector<int>& coins, int amount) {
    int n = coins.size();


    vector<vector<int>> dp(n + 1, vector<int>(amount + 1, 0));  //2D vector for storing the results of subproblems


    for (int i = 0; i <= n; i++) {
        dp[i][0] = 0;   // Initialize to 0 (base case)
    }

    for (int j = 1; j <= amount; j++) {
        dp[0][j] = INT_MAX; // Initialize to infinity
    }

    // Filling the dp table
    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= amount; j++) {
            if (coins[i - 1] > j) {
                dp[i][j] = dp[i - 1][j];
            } else {
                dp[i][j] = min(dp[i - 1][j], 1 + dp[i][j - coins[i - 1]]);
            }
        }
    }

    return dp[n][amount];
}

int main() {
    vector<int> coins = {1, 5,6, 9};
    int amount = 10;

    int min_num_coins = minCoins(coins, amount);
    cout << "Minimum number of coins required: " << min_num_coins << endl;

    return 0;
}
```

### print all the coins taken

```cpp
#include <iostream>

#include <vector>

#include <climits>
using namespace std;

struct CoinResult {
int minCoins;
vector<int> coinsUsed;
};

  

CoinResult minCoins(vector<int>& coins, int amount) {

int n = coins.size();

// dp table to store the minimum number of coins and the coins used

vector<vector<int>> dp(n + 1, vector<int>(amount + 1, INT_MAX)); // Initialize to infinity

  

// Base case: 0 coins required for amount 0

for (int i = 0; i <= n; ++i) {

dp[i][0] = 0;

}

  

// Filling the dp table

for (int i = 1; i <= n; ++i) {

for (int j = 1; j <= amount; ++j) {

if (coins[i - 1] <= j) {

int take = dp[i][j - coins[i - 1]];

if (take != INT_MAX)

dp[i][j] = min(dp[i - 1][j], 1 + take);

else

dp[i][j] = dp[i - 1][j];

} else {

dp[i][j] = dp[i - 1][j];

}

}

}

  

// Reconstruct coins used

vector<int> coinsUsed(n, 0);

int i = n, j = amount;

while (i > 0 && j > 0) {

if (dp[i][j] == dp[i - 1][j]) {

// Coin not used

--i;

} else {
// Coin used
coinsUsed[i - 1]++;
j -= coins[i - 1];
}
}

CoinResult result;
result.minCoins = dp[n][amount];
result.coinsUsed = coinsUsed;
return result;
}

  

int main() {
vector<int> coins = {1, 5, 6, 9};
int amount = 11;
CoinResult result = minCoins(coins, amount);
int min_num_coins = result.minCoins;
vector<int> coins_taken = result.coinsUsed;
cout << "Minimum number of coins required: " << min_num_coins << endl;
cout << "Coins taken: ";
for (int i = 0; i < coins.size(); ++i) {
for (int j = 0; j < coins_taken[i]; ++j) {
cout << coins[i] << " ";
}
}

cout << endl;
return 0;

}
```


