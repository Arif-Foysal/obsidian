#PHP #oop 

Inheritance is a fundamental concept in object-oriented programming (OOP) where a class can inherit properties and methods from another class. Here child class will inherit all or a few member functions and variables of a parent class. We can define an inherited class by using the `extends` keyword.

**Example:**

```php
<?php

// Parent class
class Vehicle {
    public $make;
    public $model;

    public function __construct($make, $model) {
        $this->make = $make;
        $this->model = $model;
    }

    public function start() {
        echo "The vehicle is starting...\n";
    }
}

// Child class inheriting from Vehicle
class Car extends Vehicle {
    public $doors;

    public function __construct($make, $model, $doors) {
        parent::__construct($make, $model); // Call the parent class constructor
        $this->doors = $doors;
    }

    public function start() { //method overriding
        echo "The car is starting...\n";
    }

    public function openTrunk() {
        echo "The trunk is now open.\n";
    }
}

// Create an instance of the Car class
$myCar = new Car("Toyota", "Corolla", 4);
$myCar->start(); // Output: The car is starting...
$myCar->openTrunk(); // Output: The trunk is now open.

?>
```


- #### Method overriding
	A child class can override a method from the parent class by defining a method with the same name. In the example, the `start` method in the `Car` class overrides the `start` method in the `Vehicle` class.
- ## `parent::` Keyword:
	The `parent::` keyword is used to call a method or [[PHP Constructors and Destructors]] from the parent class.
- ## Access to Parent Class Properties and Methods:
	 The child class inherits all public and protected properties and methods of the parent class, allowing them to be used or overridden as needed.
### Final Keyword

The **final** keyword can be used to **prevent** method overriding or to prevent class inheritance. 

**Example:**

```php
<?php
final class Employee {
  // some code
}
// This will result in error as the final keyword is used
class human extends Employee {
  // some code
}
?>
```
- **`final` Class:**
    
    - A `final` class cannot be extended by any other class. This is useful when you want to prevent further inheritance and ensure that the class's implementation remains unchanged.
- **`final` Method:**
    
    - A `final` method in a class cannot be overridden by child classes. This is useful when you want to ensure that a specific method's behavior remains consistent and is not altered in derived classes.

