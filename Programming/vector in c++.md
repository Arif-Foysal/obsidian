#data-structure #cpp #programming 

>[!Links]
>[[standard template library(STL)]]
>[[vector in c++#2D vector in c++]]

Vectors are the same as dynamic arrays with the ability to resize themselves automatically when an element is inserted or deleted, with their storage being handled automatically by the container. Vector elements are placed in contiguous storage so that they can be accessed and traversed using iterators.

## Declaring a vector

```cpp
vector<dataType> vectorName;
```

## Initializing a vector

We can initialize a vector in the following ways:

### 1. ****Initialization Using List****
This initialization is done with a declaration. Here, we pass the list of elements to the vector constructor to create a vector with the specified elements.
`vector<dataType> { __value1, value2, value3 ....__};`   
### 2. ****Initialization**** With a Single Value
This initialization is also done with declaration. Here, we specify the size of the vector and then initialize every element of the vector with the value.
`vector<dataType> (size, value);`   
### 3. ****Initialization From Another Vector****
This initialization is used to create a vector that is an exact copy of other_vec.
`vector<dataType> (other_vec);`
## 2D vector in c++

<iframe width=100% height="315" src="https://www.youtube.com/embed/jn8_Xq3z48w?si=ZsLoAx0QhbhqyhsC" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### How to declare a 2d vector

```cpp
vector<vector<int>> k (n+1, vector<int>(w+1));
//syntax
vector<[data type]> [name] (size, initial value); 
//vector of vector
```

## Vector Functions

Following is the list of all member functions of std::vector class in C++:

| Vector Function                                                                          | Description                                                                                             |
| ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [push_back()](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/)       | Adds an element to the end of the vector.                                                               |
| [pop_back()](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/)        | Removes the last element of the vector.                                                                 |
| [size()](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/)                    | Returns the number of elements in the vector.                                                           |
| [max_size()](https://www.geeksforgeeks.org/vector-max_size-function-in-c-stl/)           | Returns the maximum number of elements that the vector can hold.                                        |
| [resize()](https://www.geeksforgeeks.org/vector-resize-c-stl/)                           | Changes the size of the vector.                                                                         |
| [empty()](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/)                   | Checks if the vector is empty.                                                                          |
| [operator[]](https://www.geeksforgeeks.org/vectoroperator-vectoroperator-c-stl/)         | Accesses the element at a specific position.                                                            |
| [at()](https://www.geeksforgeeks.org/vectorat-vectorswap-c-stl/)                         | Accesses the element at a specific position, with bounds checking.                                      |
| [front()](https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/)                   | Accesses the first element of the vector.                                                               |
| [back()](https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/)                    | Accesses the last element of the vector.                                                                |
| [begin()](https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/)                    | Returns an iterator pointing to the first element of the vector.                                        |
| [end()](https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/)                      | Returns an iterator pointing to the past-the-end element of the vector.                                 |
| [rbegin()](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/)      | Returns a reverse iterator pointing to the last element of the vector.                                  |
| [rend()](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/)        | Returns a reverse iterator pointing to the element preceding the first element of the vector.           |
| [cbegin](https://www.geeksforgeeks.org/vector-cbegin-vector-cend-c-stl/)                 | Returns const_iterator to beginning                                                                     |
| [cend](https://www.geeksforgeeks.org/vector-cbegin-vector-cend-c-stl/)                   | Returns const_iterator to end                                                                           |
| [crbegin](https://www.geeksforgeeks.org/vectorcrend-vectorcrbegin-examples/)             | Returns const_reverse_iterator to reverse beginning                                                     |
| [crend](https://www.geeksforgeeks.org/vectorcrend-vectorcrbegin-examples/)               | Returns const_reverse_iterator to reverse end                                                           |
| [insert()](https://www.geeksforgeeks.org/vector-insert-function-in-cpp-stl/)             | Inserts elements at a specific position in the vector.                                                  |
| [erase()](https://www.geeksforgeeks.org/vector-erase-and-clear-in-cpp/)                  | Removes elements from a specific position or range in the vector.                                       |
| [swap()](https://www.geeksforgeeks.org/vectorat-vectorswap-c-stl/)                       | Swaps the contents of the vector with those of another vector.                                          |
| [clear()](https://www.geeksforgeeks.org/vector-erase-and-clear-in-cpp/)                  | Removes all elements from the vector.                                                                   |
| [emplace()](https://www.geeksforgeeks.org/vector-emplace-function-in-c-stl/)             | Constructs and inserts an element in the vector.                                                        |
| [emplace_back()](https://www.geeksforgeeks.org/vectoremplace_back-c-stl/)                | Constructs and inserts an element at the end of the vector.                                             |
| [assign()](https://www.geeksforgeeks.org/vector-assign-in-c-stl/)                        | Assigns new values to the vector elements by replacing old ones.                                        |
| [capacity()](https://www.geeksforgeeks.org/vector-capacity-function-in-c-stl/)           | Returns the size of the storage space currently allocated to the vector.                                |
| [reserve()](https://www.geeksforgeeks.org/using-stdvectorreserve-whenever-possible/)     | Requests that the vector capacity be at least enough to contain a specified number of elements.         |
| [shrink_to_fit()](https://www.geeksforgeeks.org/vector-shrink_to_fit-function-in-c-stl/) | Reduces memory usage by freeing unused space.                                                           |
| [data()](https://www.geeksforgeeks.org/vector-data-function-in-c-stl/)                   | Returns a direct pointer to the memory array used internally by the vector to store its owned elements. |
| [get_allocator](https://www.geeksforgeeks.org/get_allocator-in-cpp/)                     | Returns a copy of the allocator object associated with the vector.                                      |

**ref:** https://www.geeksforgeeks.org/vector-in-cpp-stl/
