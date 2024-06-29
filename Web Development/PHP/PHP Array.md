#PHP 

Array in php is also known as a subscript variable.

**Example:**

```php
<?php
$age = array("Virat"=>"35", "Arshdeep"=>"37", "Rohit"=>"43");
echo "Virat is " . $age['Virat'] . " years old.";
?>
```

### Types of arrays in PHP
3 types of arrays in PHP:
1. **Numeric Array**
2. **Associative Array**
3. **Multidimensional Array**

### 1. Numeric Array

These are arrays with a numeric index where values are stored and accessed in a linear fashion. 

**Example:**

```php
<?php
$bike = array("TVS", "YAMAHA", "RAJDOOT");
echo "I like " . $bike[0] . ", " . $bike[1] . " and " . $bike[2] . ".";
?>
```

### **2. Associative Array**

These are arrays with string as an index where it stores element values associated with **key values**.

**Example:**

```php
<?php
$age = array("Ben"=>"35", "Stokes"=>"37", "Jimi"=>"43");
echo "Ben is " . $age['Ben'] . " years old.";
?>
```

### **3. Multidimensional Arrays**

 A multidimensional Array is an array containing one or more arrays(array of array) where values are accessed using multiple indices.

**Example:**

```php
<?php
$cars = array (
  array("Volvo",22,18),
  array("BMW",15,13),
  array("Saab",5,2),
  array("Land Rover",17,15)
);
echo $cars[0][0].": In stock: ".$cars[0][1].", sold: ".$cars[0][2].".<br>";
?>
```

### **Array Operations**

**Adding elements**
```php
<?php
$myArray = array(); // Creating an empty array

// Adding elements to the array
$myArray[] = 1;
$myArray[] = 2;
$myArray[] = 3;

// Printing the array
print_r($myArray);
?>

```

**Removing Elements**

```php
<?php
$myArray = array(1, 2, 3, 4, 5);

// Removing the last element
array_pop($myArray);

// Removing the first element
array_shift($myArray);

// Printing the array
print_r($myArray);
?>
```

**Accessing Elements**
```php
<?php
$myArray = array(10, 20, 30);

// Accessing elements
echo $myArray[0]; // Outputs 10
echo $myArray[1]; // Outputs 20
echo $myArray[2]; // Outputs 30
?>
```

**Removing nth element**
```php
<?php
$myArray = array(1, 2, 3, 4, 5);

// Define the index of the element you want to remove
$n = 2; // This will remove the third element (index 2)

// Check if the index exists in the array
if (isset($myArray[$n])) {
    unset($myArray[$n]); // sets the value to NULL
}

// Reindex the array to maintain sequential keys if necessary
$myArray = array_values($myArray);

// Printing the array
print_r($myArray);
?>
```

**Inserting nth element**
```php
<?php
$myArray = array(1, 2, 3, 4, 5);

// Define the index where you want to insert the new element
$n = 2; // This will insert at the third position (index 2)
$newElement = 99; // The new element to insert

// Inserting the new element
array_splice($myArray, $n, 0, $newElement);

// Printing the array
print_r($myArray);
?>

```

**Updating nth element**

You already know this you dumb !!
