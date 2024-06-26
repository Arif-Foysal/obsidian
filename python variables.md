#python 

Python has no command for declaring a variable.
A variable is created the moment you first assign a value to it.
```python
x = 5  
y = "John"  
print(x)  
print(y)
```

Variables do not need to be declared with any particular type, and can even change type after they have been set.

```python
x = 4       # x is of type int  
x = "Sally" # x is now of type str  
print(x)
```

## Casting

If you want to specify the data type of a variable, this can be done with casting.
```python
x = str(3)    # x will be '3'  
y = int(3)    # y will be 3  
z = float(3)  # z will be 3.0
```
See [[python data types]] 

## Get the data type
```python
x = 5  
y = "John"  
print(type(x))  
print(type(y))
```

