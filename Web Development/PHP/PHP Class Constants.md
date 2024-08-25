#PHP 

PHP class constants are similar to regular constants but are associated with a class. They are immutable values that belong to the class rather than an instance of the class. Meaning they can be accessed without creating an object of the class.

## Declaring a Class constant
- You declare a class constant using the `const` keyword.
- Class constants must be assigned a value when they are declared.
- The value of a class constant cannot be changed once it is set.

```php
class MyClass {
    const MY_CONSTANT = "Hello, World!";
}
```
## Accessing the class constant
- You can access a class constant using the class name followed by the scope resolution operator `::` and the constant name.
	```php
	echo MyClass::MY_CONSTANT; // Outputs: Hello, World!
	```

- If you're accessing the constant within the class itself, you can use `self::CONSTANT_NAME`.
	```php
	class MyClass {
    const MY_CONSTANT = "Hello, World!";

    public function displayConstant() {
        echo self::MY_CONSTANT; // Accessing the constant within the class
	    }
	}

	$obj = new MyClass();
	$obj->displayConstant(); // Outputs: Hello, World!
	```


## Inheritance and class constants
- Class constants can be inherited by child classes.
- You can access a parent class constant from a child class using `parent::CONSTANT_NAME`.
- If a child class defines a constant with the same name as a parent class, the child class’s constant will override the parent’s constant within that child class.
```php
class ParentClass {
    const PARENT_CONSTANT = "Parent constant value";
}

class ChildClass extends ParentClass {
    const CHILD_CONSTANT = "Child constant value";

    public function displayConstants() {
        echo self::CHILD_CONSTANT;  // Outputs: Child constant value
        echo parent::PARENT_CONSTANT; // Outputs: Parent constant value
    }
}

$child = new ChildClass();
$child->displayConstants();
```
