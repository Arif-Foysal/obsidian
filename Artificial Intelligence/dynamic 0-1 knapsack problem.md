#dynamicProgramming #Algorithm #Computer-Science 

>[!Links]
>[[dynamic 0-1 knapsack problem print the items taken]]

### To-DO
- [ ] Modify code to print the items that are taken.

## Tabular method
>[!Note]
>If you are still confused, refer the book [[Grokking Algorithms]] for clarification.


This method is also knows as bottom-up method.
[[vector in c++]]


### My thoughts
On each iteration, we are basically determining whether we are taking the given item or not. 
If our available weight is less than the weight of the item,
	we do not take the item, therefore the max profit would be equal to the profit without taking the item. 
If our available weight is more or equal to the weight of the item,
	Now we have to decide if taking the item would be profitable or not,
		max(profit without taking the item, profit of taking the item + max possible profit of the remaining weight we have)


First working  code :p
```cpp
#include<iostream>
#include<math.h>
#include<vector>
using namespace std;
int knapsack(int weight[], int value[], int n, int w ){ 
//init a 2d vector/array
vector<vector<int>> k(n+1, vector<int>(w+1));
for (int i = 0; i <= n; i++) // Items row
{
for (int j = 0; j <= w; j++) //current weights column
{
if (i==0||j==0)
{
k[i][j]=0;
}

else if (weight[i-1] <= j) //item can be taken (will take if taking it would be profitable and vise versa)
{
int remainingWeight = j - weight[i-1];
int max_profit_remainingWeight= k[i-1][remainingWeight];
k[i][j] = max(k[i-1][j], value[i-1] + max_profit_remainingWeight);
}
else{ // item can not be taken
k[i][j] = k [i-1][j];
}
}
}
return k[n][w];
}
  
int main(){
int n;
cout << "Enter numebr of elements:\n";
cin >>n;
int weights[n], values[n];
for (int i = 0; i < n; i++)
{
cout << "Item"<< i+1 << " weight: ";
cin >> weights[i];
cout << "Item"<< i+1 << " value: " ;
cin >> values[i];
}

int capacity;
cout << "Enter knapsack capacity: ";
cin >> capacity; 
int result= knapsack(weights,values,n,capacity);
cout << "Result: "<< result<<endl;
return 0;
}
```

**You can definitely use 2d array instead of 2d vector** in case you forget how to declare 2d vector.

![[dynamic 0-1 knapsack problem print the items taken]]

### Maximum total profit given instead of maximum total weight

```cpp

```



**ref:**
1. [[Grokking Algorithms]]
2. https://www.geeksforgeeks.org/0-1-knapsack-problem-dp-10/
