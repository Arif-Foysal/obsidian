#python 

Unlike other programming languages, where we use indentation for readability, the indentation in python is very important.

```python
if 5 > 2:  
  print("Five is greater than two!")
```
This will run as expected.

```python
if 5 > 2:  
print("Five is greater than two!")
```
Skipping indentation will give an error.

### Another thing to keep in mind
The number of spaces is up to you as a programmer, the most common use is four, but it has to be at least one.

>You have to use the same number of spaces in the same block of code, otherwise Python will give you an error:

```python
if 5 > 2:  
 print("Five is greater than two!")  
        print("Five is greater than two!")
```
>**output**: Syntax error


