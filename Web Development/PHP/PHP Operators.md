#PHP 

PHP has different types of operators for different operations. They are as follows:

### 1. Arithmetic Operators

Arithmetic operators are used to perform arithmetic operations.

|   |   |   |
|---|---|---|
|**Name**|**Operator**|**Example**|
|Addition|+|$x+$y|
|Subtraction|-|$x-$y|
|Multiplication|*|$x*$y|
|Division|/|$x/$y|
|Modulus|%|$x%$y|
|Exponentiation|**|$x**$y|

### 2. Assignment Operators

These operators are used to assign values to variables.

|   |   |
|---|---|
|**Name**|**Evaluated as**|
|=|a=b|
|+=|a=a+b|
|-=|a=a-b|
|*=|a=a*b|
|/=|a=a/b|
|%=|a=a%b|

### 3. Comparison Operators

These operators are used to compare two values.

|   |   |   |
|---|---|---|
|**Name**|**Operator**|**Example**|
|Equal|==|$x==$y|
|Identical|===|$x===$y|
|Not equal|!=|$x!=$y|
|Not equal|<>|$x<>$y|
|Not Identical|!===|$x!===$y|
|Greater than|>|$x>$y|
|Less than|<|$x<$y|
|Greater than or equal to|>=|$x >= $y|
|Less than or equal to|<=|$x <= $y|
|Spaceship|<=>|$x <=> $y|

### 4. PHP Increment/ Decrement Operators

These operators are used to increment/ decrement variable’s value. 

|   |   |
|---|---|
|**Name**|**Operator**|
|Pre-Increment|++$x|
|Post-Increment|$x++|
|Pre-decrement|–$x|
|Post-decrement|$x- -|

### 5. PHP Logical Operators

These are the logical operators that combine conditional statements.

|   |   |   |
|---|---|---|
|**Name**|**Operator**|**Example**|
|And|and|$x and $y|
|Or|or|$x or $y|
|Xor|xor|$x xor $y|
|And|&&|$x && $y|
|Or|\||$x \| $y|
|Not|!|!&x|

### 6. PHP String Operators

PHP has these two operators designed for strings.

|                          |              |                  |
| ------------------------ | ------------ | ---------------- |
| **Name**                 | **Operator** | **Example**      |
| Concatenation            | .            | $text1 . $text2  |
| Concatenation Assignment | .=           | $text1 .= $text2 |
##### Example:
**Concatenation**
```php
$a = "hello "
$a .= "world";
// $a = "hello world"
$b = $a ."";

```
### 7. PHP Array Operators

These Operators are used to compare arrays.

|   |   |   |
|---|---|---|
|**Name**|**Operator**|**Example**|
|Union|+|$x + $y|
|Equality|==|$x = $y|
|Identity|===|$x === $y|
|Inequality|!=|$x != $y|
|Inequality|<>|$x <> $y|
|!== Non-Identity|!==|$x !== $y|

### 8. PHP Conditional Operators

These operators assign values to operands based on the outcome of a certain condition. 

| **Name**        | **Operator** | **Example**             |
| --------------- | ------------ | ----------------------- |
| Ternary         | ?:           | $x = exp1 ? exp2 : exp3 |
| Null Coalescing | ??           | $x = exp1 ?? exp2       |
**PHP Ternary Operator**

`(condition) ? True Statement : False Statement`
Example:
```php
($x == $y) ? $z = 4 : $z = 0;
//if-else version
if($x == $y){
	$z = 0;
}
else{
$z = 0;
}
```

**ref:** https://www.codewithharry.com/tutorial/php-operators/

