#PHP #webDevelopment 

Constants are like variables, except that once they are defined they cannot be changed or undefined.
A valid constant name starts with a letter or underscore (no $ sign before the constant name).
>[!Note]
>Unlike variables, constants are automatically global across the entire script.

## Create a PHP Constant
To create a constant, use the `define()` function.
### Syntax

`define(_name_, _value_, _case-insensitive_)`

**Parameters:**
- _name_: Specifies the name of the constant
- _value_: Specifies the value of the constant
- _case-insensitive_: Specifies whether the constant name should be case-insensitive. Default is false. **Note:** Defining case-insensitive constants was deprecated in PHP 7.3. PHP 8.0 accepts only false, the value true will produce a warning.
