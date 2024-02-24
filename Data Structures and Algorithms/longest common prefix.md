#Algorithm #recursion #assignment 
[[prefix]]
**Ref:** https://www.geeksforgeeks.org/longest-common-prefix-using-sorting/

<iframe width="560" height="315" src="https://www.youtube.com/embed/wtOQaovlvhY?si=LECK97cPO828zlCV" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


**Problem Statement**
Given a set of strings, find the longest common prefix.
**Examples:**

> **Input**: {“geeksforgeeks”, “geeks”, “geek”, “geezer”}  
> **Output:** “gee”
> 
> ****Input:**** {“apple”, “ape”, “april”}  
> ****Output:**** “ap”


## Naive approach (brute force)




## Divide and conquer approach
[[divide and conquer]]

```cpp
#include<iostream>
#include<string.h>
#include<math.h>

using namespace std;
 

string commonprefix(string left, string right){

int maxsize=min(left.size(),right.size());

string res="";

  

for(int i=0;i<maxsize;i++){

if (left[i]==right[i]){

res+=left[i];

}

else{

break;

}

}

return res;

}
string longestCommonPrefix(string arr[], int low, int high){

if (low>=high)

{
return arr[low];

}

int mid=(low + high)/2;

string leftstring=longestCommonPrefix(arr,low,mid);
string rightstring=longestCommonPrefix(arr,mid+1,high);

return commonprefix(leftstring,rightstring);
} 

int main(){

int n;

cout<<"Enter number of words:"<<endl;

cin >>n;

cout<<"Enter "<<n<<" words:"<<endl;

string words[n];

for(int i=0;i<n;i++){

cin>>words[i];

}

int count = sizeof(words)/sizeof(words[0]);

for (int i = 0; i < count; i++)

{
cout<< words[i]<<endl;
}

string res=longestCommonPrefix(words,0,count-1);

cout << "Longest common prefix:"<<endl;

cout <<res<<endl;

}
```

