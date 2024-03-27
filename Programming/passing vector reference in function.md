#cpp 


```cpp
#include <iostream>
#include <vector>
using namespace std;
// Function that modifies the vector passed by reference
void modifyVector(vector<int> &vec) {
    // Modify the vector as needed
    vec.push_back(100); // For example, adding an element to the vector
}

int main() {
    vector<int> myVector = {1, 2, 3, 4, 5};
    // Call the function passing the vector by reference
    modifyVector(myVector);
    // Print the modified vector
    for (int num : myVector) {
        cout << num << " ";
    }
    cout << endl;
    return 0;
}
```


