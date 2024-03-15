#programming #recursion 

**References:**
Video tutorial-
https://www.youtube.com/watch?v=oSQbwlepoCU
GFG-
https://www.geeksforgeeks.org/cpp-recursion/

>[!Contents]
>[[memory management in recursion]]
>[[fibonacci series using recursion]]
>


## What is recursion

Recursion is a technique in which a function calls itself until a given condition is satisfied. In other words, recursion is a process of solving a problem by breaking it down into smaller, simpler sub-problems.

### Syntax Structure of Recursion
```
return_type _****recursive_func****_ {  
    ....  
       __// Base Condition__  
       __// Recursive Case__  
       ....  
}
```

### Recursive Function
A function that calls itself is called a ****recursive function****. When a recursive function is called, it executes a set of instructions and then calls itself to execute the same set of instructions with a smaller input. This process continues until a base case is reached, which is a condition that stops the recursion and returns a value.

## Base Condition

A base condition is the condition that is used to terminate the recursion. The recursive function will keep calling itself till the base condition is satisfied.

## Recursive Case

Recursive case is basically the way to reach the base condition. 
It is the way in which the recursive call is present in the function. Recursive case can contain multiple recursive calls, or different parameters such that at the end, the base condition is satisfied and the recursion is terminated.

## Types of recursion

There are two different types of recursion which are as follows:

1. [[direct recursion]]
2. [[indirect recursion]]


## Examples of c++ recursion

### c++ program to calculate the sum of first n natural

```cpp
#include<iostream>
using namespace std;

int nsum(int n){
if (n==0){ //Base condition to terminate the recursion
	return 0;
	}
	
return n+(nsum(n-1)); //Recursive case to reach the base case
}

int main(){
int n;
cout << "Enter n:"<<endl;
cin >> n;
int res=nsum(n);
cout<< "nsum:"<< res<<endl;
return 0;
}
```

![[recursion.png]]

### Fibonacci series using recursion

![[fibonacci series using recursion]]
### Factorial using recursion

Learn about [[factorial]]

```cpp
#include<iostream>

using namespace std; 
int factorial(int n){
// base
if (n==0 || n==1)
{
return 1;
}

//recursive
return n * factorial(n-1);
}

int main(){
cout<<"Enter n:"<<endl;
int n;
cin>>n;
cout << factorial(n)<<endl;

return 0;
}
```


### recursive program to calculate the power of x^y, where y is a non-negative integer
#todo 
- [ ] learn this.

```
m**n = m*(m**(n-1)

3**0=1
3**1=3
3**2=9
3**4=27 // 3 * (3**(n-1)) 
```

```cpp
#include<iostream>
using namespace std;

int power(int m,int n){ //m**n
if (n==0)//base conditions
{
return 1;
}

else if (n==1)
{
return m;
} 

//recursive
return m * (power(m,n-1));
}


int main(){

int m,n; // m**n
cout<< "m**n"<<endl;
cout<<"Enter m:"<<endl;
cin >>m;
cout<<"Enter n:"<<endl;
cin >>n;
cout << power(m,n)<<endl;

return 0;

}
```