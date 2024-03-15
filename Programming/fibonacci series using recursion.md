#Algorithm #recursion #math 

Learn more about [[fibonacci series]]
### Fibonacci series using recursion



```cpp
#include<iostream>

using namespace std;

int fib(int n){

//base condition

if (n==0)

{

return 0;

}

else if (n==1||n==2)

{

return 1;

}

else{

int res=fib(n-1)+fib(n-2);//recursive condition

return res;

}

  
  

}

int main(){

cout<< "Enter a number for fibonacci series:"<<endl;

int n;

cin >> n;

  
  

for (int i = 0; i < n; i++)

{

cout << fib(i)<<" ";

}

cout<<endl;

  

return 0;

}
```

**Output**
```
Fibonacci series of 5 numbers is: 0 1 1 2 3
```
