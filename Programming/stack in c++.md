#cpp #programming #data-structure 

For creating  a [[stack]], we must include the <stack> header file in our code. We then use this syntax to define the 
`std::stack:`

## example of stack
```cpp
#include <iostream> 
#include <stack>
using namespace std;
int main() {
	stack<int> stack;
	stack.push(21);// The values pushed in the stack should be of the same data which is written during declaration of stack
	stack.push(22);
	stack.push(24);
	stack.push(25);
	int num=0;
	stack.push(num);
	stack.pop();
	stack.pop();
	stack.pop();
	while (!stack.empty()) {
		cout << stack.top() <<" ";
		stack.pop();
	}
}
```
**Output**
`22 21`
**Code Explanation:**

1. Include the iostream header file or <iostream> in our code to use its functions.
2. Include the stack header file in our code to use its functions if already included <iostream> then no need of stack header file because it has already inbuilt function in it.
3. Include the std namespace in our code to use its classes without calling it.
4. Call the main() function. The program logic should be added within this function.
5. Create a stack to store integer values.
6. Use the push() function to insert the value 21 into the stack.
7. Use the push() function to insert the value 22 into the stack.
8. Use the push() function to insert the value 24 into the stack.
9. Use the push() function to insert the value 25 into the stack.
10. Use a integer variable “num” to enter a variable value. Here its value is 0, but we can assign any integer value using cin >> num.
11. Use the push() function to insert the value of “num” variable.
12. Use the pop() function to remove the top element from the stack, that is, 25. The top element now becomes 24.
13. Use the pop() function to remove the top element from the stack, that is, 24. The top element now becomes 22.
14. Use a while loop and empty() function to check whether the stack is NOT empty. The ! is the NOT operator. So, when stack is not empty then empty() function will return false and NOT operator convert it in true and the while loop keep running. But, when the stack become empty then empty() function will return true and NOT operator will make it false and the loop come to an end.
15. Printing the current contents of the stack on the console.
16. Call the pop() function on the stack.
17. End of the body of the while loop.
18. End of the main() function body.


## The functions associated with stack are:
[empty()](https://www.geeksforgeeks.org/stack-empty-and-stack-size-in-c-stl/) – Returns whether the stack is empty – Time Complexity : O(1)   
[size()](https://www.geeksforgeeks.org/stack-empty-and-stack-size-in-c-stl/) – Returns the size of the stack – Time Complexity : O(1)   
[top()](https://www.geeksforgeeks.org/stack-top-c-stl/) – Returns a reference to the top most element of the stack – Time Complexity : O(1)   
[push(g)](https://www.geeksforgeeks.org/stack-push-and-pop-in-c-stl/) – Adds the element ‘g’ at the top of the stack – Time Complexity : O(1)   
[pop()](https://www.geeksforgeeks.org/stack-push-and-pop-in-c-stl/) – Deletes the most recent entered element of the stack – Time Complexity : O(1)

