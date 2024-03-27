#Algorithm #cpp #GreedyAlgorithm 

>[!Links]
>[[dynamic coin change problem]]

Given a value of **V** TAKA and an **infinite supply** of coins/notes valued {1, 2, 5, 10, 20, 50, 100, 500, 1000}. The task is to find minimum number of coins/notes needed to make the change.
>[!Note]
>It's like you're a cashier, trying to make the change with a set of notes/coins you have. 

>**Example**
>**Input:** V = 70  
>**Output:** 2  
>**Explanation:** We need a 50 Taka note and a 20 Taka note.
>**Input:** V = 121  
>**Output:** 3  
>**Explanation:** We need a 100 Taka note, a 20 Taka note, and a 1 Rs coin.

## Approach

Take greater coins first. This will minimize the number of coins needed to make the change.

- Sort the array of coins in descending order.
- Initialize the **result** vector as empty
- Find the largest coin that is smaller or equal to the **remaining** amount
	- Add the coin to **result** vector and
- If **remaining** becomes 0, then print the **result** else repeat.


```cpp
#include<iostream>
#include<vector>
using namespace std;
void min_coin_change(int amount){
//coins should be sorted descending order
int coins[]={1000,500,200,100,50,20,10,5,2,1};
int size=sizeof(coins)/sizeof(coins[0]);
vector<int> result;
for (int i = 0; i < size; i++)
{
while (amount>=coins[i])
{
result.push_back(coins[i]);
amount-=coins[i];
}
}
cout << "number of coins needed:\n";
cout << result.size()<<endl;
cout << "Coins are:\n";
for (int i = 0; i < result.size(); i++)
{
cout << result[i]<< " ";
}
}

int main(){
int amount;
cout << "Enter amount that you wanna change:\n";
cin >>amount;
min_coin_change(amount);
return 0;
}
```



## The issue:
Greedy method dooes not always give correct answer all the time. For example:
```
coins = [9, 6, 5, 1]
amount = 11

Using greedy coin change, answer is =[9,1,1] //3 coins
But it is not the minimum # of coins.
Minimum # of coins to change 11$ would be =[6,5]
```

To solve the issue, [[dynamic coin change problem]] comes in.


