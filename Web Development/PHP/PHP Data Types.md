#php #webDevelopment 

PHP supports the following data types:

- String
- Integer
- Float (floating point numbers - also called double)
- Boolean
- [[PHP Array]]
- Object
- NULL
- Resource
```php
<?php
	$a = "Hello world!"; //string
	$b = 100; //integer
	$c = 10.45; //float
	$d = true; //boolean
	$cars = array("Volvo","BMW","Toyota"); //array
?>
```

We can find what data type a variable is with the `var_dump()` function.
```php
var_dump($x);
```
This will return the data type the variable `$x` is.
## PHP Object
Classes and objects are the two main aspects of object-oriented programming.
### What is a class and an object?
A class is a template for objects, and an object is an instance of a class.
When the individual objects are created, they inherit all the properties and behaviors from the class, but each object will have different values for the properties.

### Constractor
If you create a __construct() function, PHP will automatically call this function when you create an object from a class.

```php
<?php  
class Car {  
  public $color;  
  public $model;  
  public function __construct($color, $model) {  
    $this->color = $color;  
    $this->model = $model;  
  }  
  public function message() {  
    return "My car is a " . $this->color . " " . $this->model . "!";  
  }  
}  
  
$myCar = new Car("black", "Volvo"); //creating an object of the class Car  
echo $myCar -> message();  
echo "<br>";  
$myCar = new Car("red", "Toyota");  
echo $myCar -> message();  
?>
```

## PHP null value
A variable of data type NULL is a variable that has no value assigned to it. 
>[!note]
>if a variable is created without a value, it is automatically assigned a value of NULL.
```php
<?php  
$x = "Hello world!";  
$x = null;  
var_dump($x);  
?>
```

## PHP Resource
The special resource type is not an actual data type. It is the storing of a reference to functions and resources external to PHP.
A common example of using the resource data type is a database call.

