#PHP #back-end 

A callback function is a function that is passed as an argument into another function and then called within the funciton.

Any existing function can be used as a callback function.

**A callback function can be:**
- A string representing the name of a function.
- An array where the first element is an object or class name, and the second element is the method name.
- An anonymous function (closure).

## Examples of PHP Callback Functions

#### **1. Passing a Function Name as a String**

You can pass the name of a function as a string to another function. The receiving function can then call this function.

```php
function sayHello() {
    echo "Hello, World!";
}

function executeCallback($callback) {
    // Call the passed function
    $callback();
}

executeCallback('sayHello'); // Outputs: Hello, World!
```

#### 2. Using Anonymous Functions (Closures)
You can also pass an anonymous function as a callback. Anonymous functions are useful when you need to define a function on the fly without naming it.

```php
$strings = ["apple", "orange", "banana", "coconut"];  
$lengths = array_map( function($item) { return strlen($item); } , $strings);  
print_r($lengths);  
```

#### 3. Using Method Names with Objects

If you need to use a method from an object, you can pass an array with the object and the method name.
```php
class Greeter {
    public function sayHello() {
        echo "Hello from a class method!";
    }
}

$greeter = new Greeter();

function executeCallback($callback) {
    // Call the passed method
    $callback();
}

executeCallback([$greeter, 'sayHello']); // Outputs: Hello from a class method!
```

#### **4. Built-in Functions that Use Callbacks**
Many of PHP’s built-in functions accept callbacks. For example, `array_map()`, `array_filter()`, and `usort()`.

- **`array_map()` Example:**
	```php
	function multiplyByTwo($number) {
    return $number * 2;
}

$numbers = [1, 2, 3, 4, 5];
$result = array_map('multiplyByTwo', $numbers);

print_r($result);
// Outputs: Array ( [0] => 2 [1] => 4 [2] => 6 [3] => 8 [4] => 10 )
	```

- **`array_filter()` Example:**
	```php
	function isEven($number) {
    return $number % 2 == 0;
	}
	
	$numbers = [1, 2, 3, 4, 5];
	$evens = array_filter($numbers, 'isEven');
	
	print_r($evens);
	// Outputs: Array ( [1] => 2 [3] => 4 )
	
	```

- **`usort()` Example:**
	```php
	$fruits = ["apple", "banana", "cherry", "date"];

	usort($fruits, function($a, $b) {
	    return strlen($a) - strlen($b);
	});
	
	print_r($fruits);
	// Outputs: Array ( [0] => date [1] => apple [2] => banana [3] => cherry )
	```


## Sorting an Array of Objects by a Custom Property
Imagine you have an array of user objects, and you want to sort this array based on the users' ages. You can achieve this by using a callback function with PHP's `usort()` function.
[[PHP usort() function]]

```php
// Array of users
$users = [
    ["name" => "Alice", "age" => 25],
    ["name" => "Bob", "age" => 20],
    ["name" => "Charlie", "age" => 30],
    ["name" => "Diana", "age" => 22],
];

// Callback function to compare ages
function compareAges($a, $b) {
    return $a['age'] - $b['age'];
}

// Sorting the array using usort and the callback function
usort($users, 'compareAges');

// Display the sorted array
print_r($users);
```
**Explanation**
- **Callback Function:** The `compareAges()` function is a callback function. It takes two parameters, `$a` and `$b`, representing two user arrays. It compares their `age` values and returns the difference.
    
    - If the result is negative, `$a` is considered smaller (younger) than `$b`.
    - If the result is positive, `$a` is considered larger (older) than `$b`.
    - If the result is zero, they are considered equal in terms of age.
- **`usort()` Function:** The `usort()` function sorts the `$users` array according to the result of the `compareAges()` function.

`output`
```php
Array
(
    [0] => Array
        (
            [name] => Bob
            [age] => 20
        )

    [1] => Array
        (
            [name] => Diana
            [age] => 22
        )

    [2] => Array
        (
            [name] => Alice
            [age] => 25
        )

    [3] => Array
        (
            [name] => Charlie
            [age] => 30
        )
)
```

