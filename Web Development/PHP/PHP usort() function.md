#PHP 

used to sort an array by values using a user-defined comparison function. 

This function is particularly useful when you need to sort an array based on custom criteria, such as sorting objects by a specific property or sorting multidimensional arrays by one of their keys.

- ## **Syntax**
	```php
	usort(array &$array, callable $callback): bool
	```

- ## **parameters**
	- **`$array`:** The array to be sorted. This array is passed by reference, meaning it will be modified directly.
	- **`$callback`:** The user-defined comparison function that determines the order of elements. This function must accept two arguments (the elements to compare) and return an integer:
    - A negative value if the first element should be before the second.
    - A positive value if the first element should be after the second.
    - Zero if they are equal.
- ## **Return Value**
	- Returns `true` on success or `false` on failure.

## **Example: Sorting an Array of Numbers**
[[PHP Anonymous Functions]]
```php
$numbers = [4, 2, 8, 6, 3, 7, 1, 5];

usort($numbers, function($a, $b) { //anonymous function
    return $a - $b; // Ascending order
});

print_r($numbers);
```

`output`
```php
Array
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
    [4] => 5
    [5] => 6
    [6] => 7
    [7] => 8
)
```

## **Example: Sorting an Array of Objects by a Property**
[[PHP Callback Functions]]
![[PHP Callback Functions#Sorting an Array of Objects by a Custom Property]]

## **Sorting an array of associative arrays by multiple keys**

```php
$records = [
    ['name' => 'Alice', 'age' => 25, 'salary' => 5000],
    ['name' => 'Bob', 'age' => 20, 'salary' => 4000],
    ['name' => 'Charlie', 'age' => 25, 'salary' => 5500],
];

usort($records, function($a, $b) {
    // First, sort by age (ascending)
    $result = $a['age'] - $b['age'];
    
    // If ages are the same, sort by salary (descending)
    if ($result === 0) {
        $result = $b['salary'] - $a['salary'];
    }

    return $result;
});

print_r($records);
```

`output`
```php
Array
(
    [0] => Array
        (
            [name] => Bob
            [age] => 20
            [salary] => 4000
        )

    [1] => Array
        (
            [name] => Charlie
            [age] => 25
            [salary] => 5500
        )

    [2] => Array
        (
            [name] => Alice
            [age] => 25
            [salary] => 5000
        )
)
```
## **Use Cases for `usort()`**

- **Sorting Objects:** When you have an array of objects and need to sort them by a property, like age, salary, date, etc.
- **Custom Sorting:** If you need a custom sorting logic that isn't just ascending or descending, such as sorting strings by length or sorting based on multiple criteria.
- **Complex Data Structures:** Sorting multidimensional arrays (arrays of arrays) by one or more keys.

>[!Warning]
>- **Modifies the Original Array:** `usort()` modifies the array directly since it’s passed by reference.
>- **Not Stable:** PHP's `usort()` is not a stable sort, meaning that elements considered equal by the comparison function may not retain their original order.

