#PHP #webDevelopment 

## PHP Integers

PHP provides automatic data type conversion. Meaning if you assign an [[integer]] value to a variable, the type of that variable will automatically be an integer. Then, if you assign a string to the same variable, the type will change to a string.
This automatic conversion can sometimes break your code.

PHP has the following predefined constants for integers:
- PHP_INT_MAX - The largest integer supported
- PHP_INT_MIN - The smallest integer supported
- PHP_INT_SIZE -  The size of an integer in bytes
### Checking a variable is integer
PHP has the following functions to check if the type of a variable is integer:
- is_int()
- is_integer() - alias of is_int()
- is_long() - alias of is_int()
```php
//check if a variable is integer
<?php  
$x = 5985;  
var_dump(is_int($x));  
  
$x = 59.85;  
var_dump(is_int($x));  
?>
```

## PHP Floats
PHP has the following predefined constants for floats (from PHP 7.2):
- PHP_FLOAT_MAX - The largest representable floating point number
- PHP_FLOAT_MIN - The smallest representable positive floating point number
- PHP_FLOAT_DIG - The number of decimal digits that can be rounded into a float and back without precision loss
- PHP_FLOAT_EPSILON - The smallest representable positive number x, so that x + 1.0 != 1.0
PHP has the following functions to check if the type of a variable is float:
- is_float()
- is_double() - alias of is_float()
```php
//check if a variable is float
<?php  
$x = 10.365;  
var_dump(is_float($x));  
?>
```
## PHP Infinity
A numeric value that is larger than PHP_FLOAT_MAX is considered infinite.
PHP has the following functions to check if a numeric value is finite or infinite:

- [is_finite()](https://www.w3schools.com/php/func_math_is_finite.asp)
- [is_infinite()](https://www.w3schools.com/php/func_math_is_infinite.asp)

```php
//Check if a numeric value is finite or infinite:
<?php  
$x = 1.9e411;  
var_dump($x);  
?>
```

## PHP NaN

NaN stands for Not a Number.
NaN is used for impossible mathematical operations.
PHP has the following functions to check if a value is not a number:
- [is_nan()](https://www.w3schools.com/php/func_math_is_nan.asp)
## PHP Numerical Strings

The PHP is_numeric() function can be used to find whether a variable is numeric. The function returns true if the variable is a number or a numeric string, false otherwise.

## PHP Casting Strings and Floats to Integers

Sometimes you need to cast a numerical value into another data type.
The (int), (integer), or intval() function are often used to convert a value to an integer.

```php
<?php  
// Cast float to int  
$x = 23465.768;  
$int_cast = (int)$x;  
echo $int_cast;  
  
echo "<br>";  
  
// Cast string to int  
$x = "23465.768";  
$int_cast = (int)$x;  
echo $int_cast;  
?>
```
**output-**
```php
23465  
23465
```

>[!Note]
>Casting to integer always floors out the value
