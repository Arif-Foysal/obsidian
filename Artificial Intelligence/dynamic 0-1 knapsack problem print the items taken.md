#Algorithm #dynamicProgramming #cpp 



```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

void print2DVector(const vector<vector<int>>& vec) {
for (const auto& row : vec) {
for (int elem : row) {
cout << elem << " ";
}
cout << endl;
}
}


int knapsack(int weight[], int value[], int n, int w, vector<vector<int>>& items_taken) {
// Init a 2D vector/array
vector<vector<int>> k(n + 1, vector<int>(w + 1));

for (int i = 0; i <= n; i++) { // Items row
for (int j = 0; j <= w; j++) { // Current weights column

if (i == 0 || j == 0) {
k[i][j] = 0;

} else if (weight[i - 1] <= j) { // Item can be taken

int remainingWeight = j - weight[i - 1];

int max_profit_remainingWeight = k[i - 1][remainingWeight];

if (value[i - 1] + max_profit_remainingWeight > k[i - 1][j]) {

k[i][j] = value[i - 1] + max_profit_remainingWeight;

items_taken[i][j] = 1; // Mark item as taken

} else {

k[i][j] = k[i - 1][j];

}

} else { // Item can not be taken

k[i][j] = k[i - 1][j];

}

}

}

return k[n][w];

}

  

void printItemsTaken(int weight[], vector<vector<int>>&itemsTaken, int n,int w){

cout << "Items Taken:"<<endl;

while (n > 0 && w > 0)

{

if (itemsTaken[n][w]==1)

{

cout << n<<" ";

w-=weight[n-1];

n--;

}

else{

n--;

}

}

cout << endl;

}

  

int main() {

int n = 3;

int p[3] = {10, 15, 40};

int w[3] = {1, 2, 3};

int capacity = 5;

  

vector<vector<int>> items_taken(n + 1, vector<int>(capacity + 1, 0)); // Initialize items_taken

  

int result = knapsack(w, p, n, capacity, items_taken);

cout << "Result: " << result << endl;

printItemsTaken(w, items_taken, n, capacity);

print2DVector(items_taken);

return 0;

}
```