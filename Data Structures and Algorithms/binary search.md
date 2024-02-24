#Computer-Science #programming #Algorithm 

**Ref:** https://www.geeksforgeeks.org/binary-search/

> ****Binary Search**** is defined as a [searching algorithm](https://www.geeksforgeeks.org/searching-algorithms/) used in a sorted array by ****repeatedly dividing the search interval in half****. The idea of binary search is to use the information that the array is sorted and reduce the time complexity to O(log N).

## Conditions for when to apply Binary Search in a Data Structure:

To apply Binary Search algorithm:

- The data structure must be sorted.
- Access to any element of the data structure takes constant time.

![[Pasted image 20240218140057.png]]

The ****Binary Search Algorithm**** can be implemented in the following two ways

- Iterative Binary Search Algorithm
- Recursive Binary Search Algorithm

## Iterative Binary Search Algorithm

### PHP
```php
    /**
     * @param Integer[] $nums
     * @param Integer $target
     * @return Integer
     */   
function search($nums, $target) {
    $low=0;
    $high=sizeof($nums)-1;
    echo "Initial low= ",$low," Initial high= ",$high;
        while ($low<=$high) {
            $mid=floor(($low + $high)/2);
            if ($target==$nums[$mid]) {
                return $mid;
            }
            elseif($target>$nums[$mid]){
                $low=$mid+1;
            }
            elseif($target<$nums[$mid]){
                $high=$mid-1;
            }
        }      
    return -1;
}
```

### C++

```cpp
// C++ program to implement iterative Binary Search
#include <bits/stdc++.h>
using namespace std;

// An iterative binary search function.
int binarySearch(int arr[], int l, int r, int x)
{
	while (l <= r) {
		int m = l + (r - l) / 2;

		// Check if x is present at mid
		if (arr[m] == x)
			return m;

		// If x greater, ignore left half
		if (arr[m] < x)
			l = m + 1;

		// If x is smaller, ignore right half
		else
			r = m - 1;
	}

	// If we reach here, then element was not present
	return -1;
}

// Driver code
int main(void)
{
	int arr[] = { 2, 3, 4, 10, 40 };
	int x = 10;
	int n = sizeof(arr) / sizeof(arr[0]);
	int result = binarySearch(arr, 0, n - 1, x);
	(result == -1)
		? cout << "Element is not present in array"
		: cout << "Element is present at index " << result;
	return 0;
}
```

## Recursive binary search

```cpp
int binarysearch(int arr[],int low,int high,int key){

int mid=low+(high-low)/2;
if (low>high)//base condition
{
return -1;
}

else if (arr[mid]==key)
{
return mid;
}

else if (key>arr[mid])
{
return binarysearch(arr,mid+1,high,key);
}

return binarysearch(arr,low,mid-1,key);

}
```
or,
```cpp
// C++ program to implement recursive Binary Search
#include <bits/stdc++.h>
using namespace std;

// A recursive binary search function. It returns
// location of x in given array arr[l..r] is present,
// otherwise -1
int binarySearch(int arr[], int l, int r, int x)
{
	if (r >= l) {
		int mid = l + (r - l) / 2;

		// If the element is present at the middle
		// itself
		if (arr[mid] == x)
			return mid;

		// If element is smaller than mid, then
		// it can only be present in left subarray
		if (arr[mid] > x)
			return binarySearch(arr, l, mid - 1, x);

		// Else the element can only be present
		// in right subarray
		return binarySearch(arr, mid + 1, r, x);
	}

	// We reach here when element is not
	// present in array
	return -1;
}

// Driver code
int main()
{
	int arr[] = { 2, 3, 4, 10, 40 };
	int x = 10;
	int n = sizeof(arr) / sizeof(arr[0]);
	int result = binarySearch(arr, 0, n - 1, x);
	(result == -1)
		? cout << "Element is not present in array"
		: cout << "Element is present at index " << result;
	return 0;
}
```


