#dynamicProgramming #programming #Algorithm #math 

>[!Links]
>[[fibonacci series using recursion]]


## Fibonacci series using dp
## Time Complexity

`t(n) = t(n-1) + t(n-2) + O(n)`

- [x] create vector for memoization
- [x] check if memoized solution exists.


```cpp
	#include <iostream>
using namespace std;

int fibonacciRecursion(int n, int* memo) {
if (memo[n] != 0)
return memo[n];
if (n == 1 || n == 2)
return 1;
int res = fibonacciRecursion(n - 1, memo) + fibonacciRecursion(n - 2, memo);
memo[n] = res;
return res;
}

int main() {
int num;
cout << "Enter num: ";
cin >> num;
int memo[num + 1]; // we store 0th and 1st num as 0 and 1
for (int i = 0; i <= num; i++)
memo[i] = 0; // init with 0
memo[1] = 1;
memo[2] = 1;
int res = fibonacciRecursion(num, memo);
cout << "Result: " << res << endl;
return 0;
}
```

- [x] Find why below code doesn't work- #todo
**Bugs**
```cpp
//memoization tecnique , [not memorization]
//dynamic approach
#include<bits/stdc++.h>
using namespace std;
int fibonacciRecursion(int n, int* memo){
int res;
if (memo[n]!=0)
{
return memo[n];
}
if (n==1 || n==2)
{
return memo[n];
}
else{
res=fibonacciRecursion(n-1,memo) + fibonacciRecursion(n-2,memo);
}
memo[n]=res;
return res;
}
int main(){
int num;
cout << "enter num: ";
cin >> num;
int memo[num+2]; // we store 0th and 1st num as 0 and 1
int size=sizeof(memo)/sizeof(memo[0]);
for (int i = 0; i < size; i++)
{
memo[i]=0;//init with 0
}
memo[1]=1;
memo[2]=1;
int res=fibonacciRecursion(6,memo);
cout << "result"<<endl;
cout << res;
return 0;
}
```



