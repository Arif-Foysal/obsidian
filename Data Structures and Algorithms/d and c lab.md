#Algorithm #divide-and-conquer 

```cpp
____________________________________________________________
Find the count of even numbers in an array Arr of N integers
____________________________________________________________

#include<iostream>
using namespace std;

int countEven(int Arr[],  int i,  int j  )  {
    if(i==j){
        if(Arr[i]%2==0){
            return 1;
        }
        else{
            return 0;
        }
    }
    else{
        int mid=(i+j)/2;
        int solve1 = countEven(Arr, i, mid); // solution to the first half
        int solve2 = countEven(Arr, mid+1, j); // solution to the second half
        return solve1+solve2;
    }
}


int main(){
    int n,i;
    cout<<"Enter the size of array";
    cin>>n;
    int arr[n];
    cout << "Enter the elements of the array: ";
    for (i = 0; i < n; ++i) {
        cin >> arr[i];
    }
    cout<<"The count of even number is: "<<countEven(arr,0,n-1);
    return 0;
}

____________________________________________________________
x^y
____________________________________________________________
#include <iostream>
using namespace std;

long long power(int x, int y) {
    if (y == 0) {
        return 1;
    } else {
        int mid = y / 2;
        long long p = power(x, mid);
        if (y % 2 == 0) {
            return p * p;
        } else {
            return p * p * x;
        }
    }
}

int main() {
    int x ,y;
    cout<<"Enter the number: ";
    cin>>x;
    cout<<"Enter the power: ";
    cin>>y;

    long long result = power(x, y);

    cout << x << " raised to the power of " << y << " is: " << result << endl;

    return 0;
}


____________________________________________________________
Find the max and min element of an array.
____________________________________________________________
#include<iostream>
#include<climits>
using namespace std;
pair<int, int> MaxMin(int A[], int i, int j){
    int mid;
    pair<int, int> result, leftMaxMin, rightMaxMin;
    if(i==j){
        result.first = A[i];
        result.second = A[i];
    }
    else{
        mid=(i+j)/2;
        leftMaxMin = MaxMin(A, i, mid);
        rightMaxMin = MaxMin(A, mid + 1, j);
        result.first = max(leftMaxMin .first, rightMaxMin.first);
        result.second =min(leftMaxMin .second, rightMaxMin.second);
    }
    return result;
}



int main(){
    int n,i;
    cout<<"Enter the size of array: ";
    cin>>n;
    int arr[n];
    cout << "Enter the elements of the array: ";
    for (i = 0; i < n; ++i) {
        cin >> arr[i];
    }

    pair<int, int> max_min=MaxMin(arr, 0, n - 1);
    cout << "Maximum element: " << max_min.first << endl;
    cout << "Minimum element: " << max_min.second << endl;
    return 0;
}

____________________________________________________________
Binary Search
____________________________________________________________

#include<iostream>
using namespace std;

int binary_search(int A[],int start,int end,int key){
    if(start==end){
        if(A[start]==key){
            return start;
        }
        else return -1;
    }
    else{
        int mid=(start+end)/2;
        if(A[mid]==key){
            return mid;
        }
        else if(key<A[mid]){
            return binary_search(A,start,mid-1,key);
        }
        else{
            return binary_search(A,mid+1,end, key);
        }
    }
}

int main(){
    int n,i,key, result;
    cout<<"Enter the size of array: ";
    cin>>n;
    int arr[n];
    cout << "Enter the elements of the array: ";
    for (i = 0; i < n; ++i) {
        cin >> arr[i];
    }
    cout<<"Which number you want to find? ";
    cin>>key;
    result=binary_search(arr,0,n-1,key);
    if(result!=-1)
        cout << "Found at position " << result+1 << endl;
    else
        cout << "Not Found" << endl;

    return 0;
}


____________________________________________________________
Merge Sort
____________________________________________________________
#include <iostream>
#include <vector>
using namespace std;

void merge(vector<int>& arr, int left, int middle, int right) {
    int n1 = middle - left + 1;
    int n2 = right - middle;

    vector<int> leftArray(n1);
    vector<int> rightArray(n2);

    for (int i = 0; i < n1; i++)
        leftArray[i] = arr[left + i];
    for (int j = 0; j < n2; j++)
        rightArray[j] = arr[middle + 1 + j];

    int i = 0,j = 0, k = left;

    while (i < n1 && j < n2) {
        if (leftArray[i] <= rightArray[j]) {
            arr[k] = leftArray[i];
            i++;
        } else {
            arr[k] = rightArray[j];
            j++;
        }
        k++;
    }

    while (i < n1) {
        arr[k] = leftArray[i];
        i++;
        k++;
    }

    while (j < n2) {
        arr[k] = rightArray[j];
        j++;
        k++;
    }
}

void mergeSort(vector<int>& arr, int left, int right) {
    if (left < right) {
        int middle = left + (right - left) / 2;

        mergeSort(arr, left, middle);
        mergeSort(arr, middle + 1, right);

        merge(arr, left, middle, right);
    }
}

int main() {
    vector<int> arr = {12, 11, 13, 5, 6, 7};
    int arrSize = arr.size();

    cout << "Original array: ";
    for (int num : arr) {
        cout << num << " ";
    }

    mergeSort(arr, 0, arrSize - 1);

    cout << "\nSorted array: ";
    for (int num : arr) {
        cout << num << " ";
    }

    return 0;
}



____________________________________________________________
Max Sum Subarray
____________________________________________________________
#include<iostream>
using namespace std;

int maxCrossingSum(int arr[], int start, int mid, int end){
    int sum = 0,leftSum = INT_MIN, rightSum = INT_MIN,i;

    for (i = start; i <= mid; i++) {
        sum += arr[i];
    }
    leftSum = max(leftSum, sum);

    sum = 0;
    for (i = mid + 1; i <= end; ++i) {
        sum += arr[i];
    }
    rightSum = max(rightSum, sum);

    return leftSum + rightSum;
}

int maxSumSubarray(int A[],int i, int j){
    int mid;
    if(i==j){
        return A[i];
    }
    else{
        mid=(i+j)/2;

        return max(max(maxSumSubarray(A,i,mid), maxSumSubarray(A,mid+1,j)), maxCrossingSum(A,i,mid,j));
    }
}

int main(){
    int n,i;
    cout<<"Enter the size of array: ";
    cin>>n;
    int arr[n];
    cout << "Enter the elements of the array: ";
    for (i = 0; i < n; ++i) {
        cin >> arr[i];
    }

    cout << "Maximum sum of subarray: " << maxSumSubarray(arr,0,n-1) << endl;
    return 0;
}
```