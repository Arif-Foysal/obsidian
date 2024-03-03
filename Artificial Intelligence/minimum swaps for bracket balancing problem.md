#Algorithm #GreedyAlgorithm #cpp 

>[!Links]
>
### Problem Statement

You are given a string of `2N` characters consisting of N `[` brackets and N `]` brackets. A string is considered balanced if it can be represented in the form `S2[S1]` where `S1` and `S2` are balanced strings. We can make an unbalanced string balanced by swapping adjacent characters. Calculate the minimum number of swaps necessary to make a string balanced.

**Examples:** 
```
Input  : []][][  
Output : 2  
```

**First swap**: Position 3 and 4  
`[][]][`  
**Second swap**: Position 5 and 6  
`[][][]`  

```
Input  : [[][]]  
Output : 0  
The string is already balanced.
```


<iframe width="560" height="315" src="https://www.youtube.com/embed/FaxCT9zumVs?si=kPMUIIK8nj6n0MCX" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


```cpp
#include<iostream>

#include<string.h>
using namespace std;
int minimumSwaps(string s){

int res=0;

int val=0;

for (int i = 0; i < s.length(); i++)

{

if (s[i]=='[')

{

val++;

}

else{

val--;

if (val<0)

{

res=res-val;

}

}

}

return res;

  

}

  
  

int main(){

string s;

cout<<"Enter string:";

cin >> s;

  
  
  

int a=minimumSwaps(s);

  

cout << a<<endl;

  

return 0;

}
```