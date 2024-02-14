#cpp #programming 

C++ comes with libraries that provide us with many ways for performing input and output. In C++ input and output are performed in the form of a sequence of bytes or more commonly known as **streams**.

- **Input Stream:** If the direction of flow of bytes is from the device(for example, Keyboard) to the main memory then this process is called input.
- **Output Stream:** If the direction of flow of bytes is opposite, i.e. from main memory to device( display screen ) then this process is called output.
![[C-basic-input-output.png]]


****Header files available in C++ for Input/Output operations are:**** 

1. ****iostream****: iostream stands for standard input-output stream. This header file contains definitions of objects like cin, cout, cerr, etc.
2. ****iomanip****: iomanip stands for input-output manipulators. The methods declared in these files are used for manipulating streams. This file contains definitions of setw, setprecision, etc.
3. ****fstream****: This header file mainly describes the file stream. This header file is used to handle the data being read from a file as input or data being written into the file as output.
4. [****bits/stdc++:****](https://www.geeksforgeeks.org/bitsstdc-h-c/#:~:text=C%2FC%2B%2B-,%3Cbits%2Fstdc%2B%2B.,h%3E%20in%20C%2B%2B&text=It%20is%20basically%20a%20header,your%20rank%20is%20time%20sensitive.) This header file includes every standard library. In programming contests, using this file is a good idea, when you want to reduce the time wasted in doing chores; especially when your rank is time sensitive. To know more about this header file refer [this](https://www.geeksforgeeks.org/bitsstdc-h-c/#:~:text=C%2FC%2B%2B-,%3Cbits%2Fstdc%2B%2B.,h%3E%20in%20C%2B%2B&text=It%20is%20basically%20a%20header,your%20rank%20is%20time%20sensitive.) article.

In C++ after the header files, we often use ‘__using namespace std;__‘. The reason behind it is that all of the standard library definitions are inside the namespace std. As the library functions are not defined at global scope, so in order to use them we use __namespace std__. So, that we don’t need to write STD:: at every line (eg. STD::cout etc.). To know more refer [this](https://www.geeksforgeeks.org/why-it-is-important-to-write-using-namespace-std-in-cpp-program/) article.
## cin and cout
The two instances ****cout in C++**** and ****cin in C++**** of iostream class are used very often for printing outputs and taking inputs respectively. These two are the most basic methods of taking input and printing output in C++. To use cin and cout in C++ one must include the header file __iostream__ in the program.

This article mainly discusses the objects defined in the header file __iostream__ like the cin and cout.  

- ****Standard output stream (cout)****: Usually the standard output device is the display screen. The C++ ****cout**** statement is the instance of the iostream class. It is used to produce output on the standard output device which is usually the display screen. The data needed to be displayed on the screen is inserted in the standard output stream (cout) using the insertion operator(****<<****).

```cpp
#include <iostream>
using namespace std;
int main()
{
	char sample[] = "GeeksforGeeks";
	cout << sample << " - A computer science portal for geeks";
	return 0;
}
```
**Output**
```
GeeksforGeeks - A computer science portal for geeks
```
****Time Complexity:**** O(1)  
****Auxiliary Space:**** O(1)

In the above program, the insertion operator(****<<****) inserts the value of the string variable ****sample**** followed by the string “A computer science portal for geeks” in the standard output stream ****cout**** which is then displayed on the screen.

- ****standard input stream (cin)****: Usually the input device in a computer is the keyboard. C++ cin statement is the instance of the class ****istream**** and is used to read input from the standard input device which is usually a keyboard.   
    The extraction operator(****>>****) is used along with the object ****cin**** for reading inputs. The extraction operator extracts the data from the object ****cin**** which is entered using the keyboard.
```cpp
#include <iostream>
using namespace std;
int main()
{
	int age;
	cout << "Enter your age:";
	cin >> age;
	cout << "\nYour age is: " << age;
	return 0;
}

```
**Input**
`18`
**Output**
```
Enter your age:  
Your age is: 18
```

The above program asks the user to input the age. The object cin is connected to the input device. The age entered by the user is extracted from cin using the extraction operator(****>>****) and the extracted data is then stored in the variable ****age**** present on the right side of the extraction operator.

- ****Un-buffered standard error stream (cerr)****: The C++ cerr is the standard error stream that is used to output the errors. This is also an instance of the iostream class. As cerr in C++ is un-buffered so it is used when one needs to display the error message immediately. It does not have any buffer to store the error message and display it later.
- The main difference between cerr and cout comes when you would like to redirect output using “cout” that gets redirected to file if you use “cerr” the error doesn’t get stored in file.(This is what un-buffered means ..It cant store the message)
```cpp
#include <iostream>

using namespace std;

int main()
{
	cerr << "An error occurred";
	return 0;
}

```
**Output**
```
An error occurred
```

- ****buffered standard error stream (clog)****: This is also an instance of ostream class and used to display errors but unlike cerr the error is first inserted into a buffer and is stored in the buffer until it is not fully filled. or the buffer is not explicitly flushed (using flush()). The error message will be displayed on the screen too.
```cpp
#include <iostream>
using namespace std;
int main()
{
	clog << "An error occurred";
	return 0;
}
```
**Output**
```
An error occurred
```

### Difference between cout, cerr and clog
1. **`cout`**:
    
    - `cout` is the standard output stream used for normal output operations. It is [[io buffer]], meaning that it collects output before displaying it, and then displays the accumulated output all at once.
    - It is generally used for displaying normal program output, such as results, prompts, or any other informational messages.
2. **`cerr`**:
    
    - `cerr` is also an output stream, but it is unbuffered. This means that it does not accumulate output before displaying it; it displays output immediately.
    - `cerr` is typically used for error messages or other urgent messages that need to be displayed immediately without buffering, such as runtime errors or debugging information.
3. **`clog`**:
    
    - `clog` is similar to `cerr` in that it is also unbuffered, meaning it displays output immediately.
    - However, `clog` is typically used for logging purposes, where you want to separate the logging output from the normal program output (`cout`). It's often used for writing informational or diagnostic messages to a log file while still displaying them immediately like `cerr`.

In summary, the main differences between `cout`, `cerr`, and `clog` are related to their buffering behavior and their intended use cases. `cout` is buffered and used for normal program output, `cerr` is unbuffered and used for error messages, and `clog` is unbuffered and used for logging purposes.

### use case of cerr and clog
`cerr` and `clog` are both used for immediate output without buffering, but they are typically used in different scenarios based on their intended purposes. Here are examples illustrating when to use each:

1. **`cerr`** (Standard Error Stream):



```cpp
#include <iostream>

int main() {
    int divisor = 0;
    
    if (divisor == 0) {
        std::cerr << "Error: Cannot divide by zero!" << std::endl;
        return 1; // Exiting program with an error status
    }
    
    int result = 10 / divisor;
    std::cout << "Result: " << result << std::endl;
    
    return 0;
}

```
In this example, `cerr` is used to immediately output an error message when an attempt to divide by zero occurs. Since `cerr` is unbuffered, the error message will be displayed immediately, which is crucial for communicating errors that require immediate attention. This helps in debugging and understanding runtime issues.

2. **`clog`** (Standard Logging Stream):

```cpp
#include <iostream>
int main() {
    // Open a log file
    std::ofstream logfile("app_log.txt");
    
    // Redirect clog to the log file
    std::clog.rdbuf(logfile.rdbuf());
    // Application logic
    std::clog << "Starting application..." << std::endl;
    // Simulated error
    std::string username;
    if (username.empty()) {
        std::clog << "Warning: Username is empty!" << std::endl;
    }
    std::clog << "Application finished." << std::endl;
    return 0;
}

```

In this example, `clog` is used for logging informational messages during the execution of the program. The `clog` stream is redirected to a log file (`app_log.txt`) using `std::clog.rdbuf(logfile.rdbuf())`. This allows all log messages sent to `clog` to be written to the log file immediately. `clog` is suitable for logging non-error information that helps in understanding the program's behavior, such as warnings or informational messages.

In summary, `cerr` is typically used for error messages and debugging output that require immediate attention, while `clog` is used for logging non-error information and diagnostics to a log file.