#PHP #webDevelopment 

## PHP pi() Function
The `pi()` function returns the value of PI:
```php
<?php  
echo(pi()); // returns 3.1415926535898  
?>
```
## PHP min() and max() Functions
The `min()` and `max()` functions can be used to find the lowest or highest value in a list of arguments:
```php
<?php  
echo(min(0, 150, 30, 20, -8, -200));  // returns -200  
echo(max(0, 150, 30, 20, -8, -200));  // returns 150  
?>
```
## PHP abs() Function
The `abs()` function returns the absolute (positive) value of a number:
```php
<?php  
echo(abs(-6.7));  // returns 6.7  
?>
```
## PHP sqrt() Function
The `sqrt()` function returns the square root of a number:
```php
<?php  
echo(sqrt(64));  // returns 8  
?>
```
## PHP round() Function
The `round()` function rounds a floating-point number to its nearest integer:
```php
<?php  
echo(round(0.60));  // returns 1  
echo(round(0.49));  // returns 0  
?>
```
## Random Numbers
The `rand()` function generates a random number:
```php
<?php  
echo(rand());  
?>
```
If you want a random number within a range, you can add the optional _min_ and _max_ parameters to specify the lowest integer and the highest integer to be returned. In this case we want a random number between 10 and 100:
```php
<?php  
echo(rand(10, 100));  
?>
```

## PHP Math Functions

|Function|Description|
|---|---|
|[abs()](https://www.w3schools.com/php/func_math_abs.asp)|Returns the absolute (positive) value of a number|
|[acos()](https://www.w3schools.com/php/func_math_acos.asp)|Returns the arc cosine of a number|
|[acosh()](https://www.w3schools.com/php/func_math_acosh.asp)|Returns the inverse hyperbolic cosine of a number|
|[asin()](https://www.w3schools.com/php/func_math_asin.asp)|Returns the arc sine of a number|
|[asinh()](https://www.w3schools.com/php/func_math_asinh.asp)|Returns the inverse hyperbolic sine of a number|
|[atan()](https://www.w3schools.com/php/func_math_atan.asp)|Returns the arc tangent of a number in radians|
|[atan2()](https://www.w3schools.com/php/func_math_atan2.asp)|Returns the arc tangent of two variables x and y|
|[atanh()](https://www.w3schools.com/php/func_math_atanh.asp)|Returns the inverse hyperbolic tangent of a number|
|[base_convert()](https://www.w3schools.com/php/func_math_base_convert.asp)|Converts a number from one number base to another|
|[bindec()](https://www.w3schools.com/php/func_math_bindec.asp)|Converts a binary number to a decimal number|
|[ceil()](https://www.w3schools.com/php/func_math_ceil.asp)|Rounds a number up to the nearest integer|
|[cos()](https://www.w3schools.com/php/func_math_cos.asp)|Returns the cosine of a number|
|[cosh()](https://www.w3schools.com/php/func_math_cosh.asp)|Returns the hyperbolic cosine of a number|
|[decbin()](https://www.w3schools.com/php/func_math_decbin.asp)|Converts a decimal number to a binary number|
|[dechex()](https://www.w3schools.com/php/func_math_dechex.asp)|Converts a decimal number to a hexadecimal number|
|[decoct()](https://www.w3schools.com/php/func_math_decoct.asp)|Converts a decimal number to an octal number|
|[deg2rad()](https://www.w3schools.com/php/func_math_deg2rad.asp)|Converts a degree value to a radian value|
|[exp()](https://www.w3schools.com/php/func_math_exp.asp)|Calculates the exponent of e|
|[expm1()](https://www.w3schools.com/php/func_math_expm1.asp)|Returns exp(x) - 1|
|[floor()](https://www.w3schools.com/php/func_math_floor.asp)|Rounds a number down to the nearest integer|
|[fmod()](https://www.w3schools.com/php/func_math_fmod.asp)|Returns the remainder of x/y|
|[getrandmax()](https://www.w3schools.com/php/func_math_getrandmax.asp)|Returns the largest possible value returned by rand()|
|[hexdec()](https://www.w3schools.com/php/func_math_hexdec.asp)|Converts a hexadecimal number to a decimal number|
|[hypot()](https://www.w3schools.com/php/func_math_hypot.asp)|Calculates the hypotenuse of a right-angle triangle|
|[intdiv()](https://www.w3schools.com/php/func_math_intdiv.asp)|Performs integer division|
|[is_finite()](https://www.w3schools.com/php/func_math_is_finite.asp)|Checks whether a value is finite or not|
|[is_infinite()](https://www.w3schools.com/php/func_math_is_infinite.asp)|Checks whether a value is infinite or not|
|[is_nan()](https://www.w3schools.com/php/func_math_is_nan.asp)|Checks whether a value is 'not-a-number'|
|[lcg_value()](https://www.w3schools.com/php/func_math_lcg_value.asp)|Returns a pseudo random number in a range between 0 and 1|
|[log()](https://www.w3schools.com/php/func_math_log.asp)|Returns the natural logarithm of a number|
|[log10()](https://www.w3schools.com/php/func_math_log10.asp)|Returns the base-10 logarithm of a number|
|[log1p()](https://www.w3schools.com/php/func_math_log1p.asp)|Returns log(1+number)|
|[max()](https://www.w3schools.com/php/func_math_max.asp)|Returns the highest value in an array, or the highest value of several specified values|
|[min()](https://www.w3schools.com/php/func_math_min.asp)|Returns the lowest value in an array, or the lowest value of several specified values|
|[mt_getrandmax()](https://www.w3schools.com/php/func_math_mt_getrandmax.asp)|Returns the largest possible value returned by mt_rand()|
|[mt_rand()](https://www.w3schools.com/php/func_math_mt_rand.asp)|Generates a random integer using Mersenne Twister algorithm|
|[mt_srand()](https://www.w3schools.com/php/func_math_mt_srand.asp)|Seeds the Mersenne Twister random number generator|
|[octdec()](https://www.w3schools.com/php/func_math_octdec.asp)|Converts an octal number to a decimal number|
|[pi()](https://www.w3schools.com/php/func_math_pi.asp)|Returns the value of PI|
|[pow()](https://www.w3schools.com/php/func_math_pow.asp)|Returns x raised to the power of y|
|[rad2deg()](https://www.w3schools.com/php/func_math_rad2deg.asp)|Converts a radian value to a degree value|
|[rand()](https://www.w3schools.com/php/func_math_rand.asp)|Generates a random integer|
|[round()](https://www.w3schools.com/php/func_math_round.asp)|Rounds a floating-point number|
|[sin()](https://www.w3schools.com/php/func_math_sin.asp)|Returns the sine of a number|
|[sinh()](https://www.w3schools.com/php/func_math_sinh.asp)|Returns the hyperbolic sine of a number|
|[sqrt()](https://www.w3schools.com/php/func_math_sqrt.asp)|Returns the square root of a number|
|[srand()](https://www.w3schools.com/php/func_math_srand.asp)|Seeds the random number generator|
|[tan()](https://www.w3schools.com/php/func_math_tan.asp)|Returns the tangent of a number|
|[tanh()](https://www.w3schools.com/php/func_math_tanh.asp)|Returns the hyperbolic tangent of a number|