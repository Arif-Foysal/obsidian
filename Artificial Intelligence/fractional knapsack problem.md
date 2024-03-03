#GreedyAlgorithm #Algorithm #programming #optimization-problem

>[!Links]
>[[fractional knapsack problem]]
>[[c++ type casting]]



Given the weights and profits of **N** items, in the form of **{profit, weight}** put these items in a knapsack of capacity **W** to get the maximum total profit in the knapsack. In **Fractional Knapsack**, we can take fraction of items for maximizing the total value of the knapsack.

**Input:** `arr[] = {{60, 10}, {100, 20}, {120, 30}}, W = 50`
**Output:** `240`

### Approach
- Calculate the ratio (**profit/weight**) for each item.
- Sort all the items in decreasing order of the ratio.
- pick the costliest(value/weight) then the next costliest and so on until we cant add an item as a whole.
- At the end add the next item as much(fraction) as you can.


```cpp
/* 
- sort the items based on value/weight rato
- pick the costliest(value/weight) then the next costliest and so on until we cant add an item as a whole
- at the end add the next item as much(fraction) as you can
*/

#include<algorithm>
#include<iostream>
using namespace std;

struct Item{
int weight;
int profit;
//constructor
// Item(int w,int p){
// this->weight=w;
// this->profit=p;
// }
};
static bool cmp(struct Item a, struct Item b)
{
double r1 = (double)a.profit / (double)a.weight;
double r2 = (double)b.profit / (double)b.weight;
return r1 > r2;
}
double fractionalKnapsack(struct Item arr[], int w, int n)
sort(arr,arr+n,cmp);
int remaining=w;
int current=0;
double netProfit=0; 

while (current < n && remaining > 0)
{
if (arr[current].weight <= remaining)
{
netProfit+=arr[current].profit;
remaining-=arr[current].weight;
}

else{
netProfit+= (arr[current].profit*remaining) / arr[current].weight;
remaining=0;
}
current++;
}
cout << "remaining: ";
cout << remaining <<endl;
return netProfit;
}

int main(){
int n,w;
cout << "Enter n:\n";
cin >>n; 
cout << "Enter w:\n";
cin >> w;
struct Item arr[n]; 

for (int i = 0; i < n; i++)
{
cout << "Enter weight("<< i <<"): ";
cin >> arr[i].weight;
cout << "Enter Profit("<< i <<"): ";
cin >> arr[i].profit;
}
double res=fractionalKnapsack(arr,w,n);
cout << "sorted:"<<endl; 

for (int i = 0; i < n; i++)
{
cout << arr[i].weight<<" ";
cout << arr[i].profit<<endl;
}

cout << "net profit: ";
cout<< res<<endl; 
return 0;
}
```

