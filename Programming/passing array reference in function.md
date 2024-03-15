#cpp 

```cpp
#include<bits/stdc++.h>

using namespace std;

void changeArray(int* arr,int size){
for(int i=0; i<size;i++){
	arr[i]=100;      //set every element of the array as 100
}

}
int main(){
int arr[2]={9,10};
changeArray(arr,2);

for (int i = 0; i < 2; i++)
{
cout << arr[i]<<endl;
}

return 0;
}
```


