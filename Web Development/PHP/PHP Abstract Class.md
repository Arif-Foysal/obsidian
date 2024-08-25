#PHP #oop 

Abstract classes and methods are used to define a blueprint for other classes.
An abstract class cannot be instantiated on its own; instead, it must be extended by other classes.

Abstract methods within an abstract class are methods that are declared but contain no implementation—they must be defined in any child class that inherits the abstract class.

>[!Note]
>An abstract class should have at least abstract method.

### **Abstract Class:**

- An abstract class is declared using the `abstract` keyword.
- It can contain both abstract methods (which are declared without implementation) and regular methods (which do have implementation).
- You cannot create an instance of an abstract class directly; it must be inherited by a subclass.

### **Abstract Methods:**

- Abstract methods are methods declared in an abstract class without any implementation.
- The `abstract` keyword is used before the method declaration.
- Any class that inherits an abstract class must implement all of its abstract methods.
- The signature (name, parameters) of the abstract method must be the same in the subclass.

## Concrete classes
- Classes that extend from abstract classes are called concrete classes.

### Example Code
```php
abstract class Animal {
    // Abstract method with no implementation
    abstract public function makeSound();

    // Regular method with implementation
    public function sleep() {
        echo "The animal is sleeping.";
    }
}

class Dog extends Animal {
    // Providing implementation for the abstract method
    public function makeSound() {
        echo "Bark!";
    }
}

class Cat extends Animal {
    // Providing implementation for the abstract method
    public function makeSound() {
        echo "Meow!";
    }
}

// Create instances of the subclasses
$dog = new Dog();
$dog->makeSound();  // Outputs: Bark!
$dog->sleep();      // Outputs: The animal is sleeping.

$cat = new Cat();
$cat->makeSound();  // Outputs: Meow!
$cat->sleep();      // Outputs: The animal is sleeping.
```

## Define abstract function that return a value:
```php
  abstract public function intro() : string; //return string
```

