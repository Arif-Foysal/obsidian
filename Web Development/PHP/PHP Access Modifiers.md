#PHP #oop 

In the PHP programming language, every property and method of a class can have access modifiers which control their accessibility in the entire program. 

There are three access modifiers in PHP:

1. **Public**
2. **Protected**
3. **Private**

Below is a table for a better understanding of the access modifiers

| Class Member Access Specifier | Access from own class | Accessible from derived class | Accessible by Object |
| ----------------------------- | --------------------- | ----------------------------- | -------------------- |
| Private                       | Yes                   | No                            | No                   |
| Protected                     | Yes                   | Yes                           | No                   |
| Public                        | Yes                   | Yes                           | Yes                  |

### Public

Public property or method can be accessed by any code whether that code is inside or outside of that class. If a property or method is declared public, then it can be accessed anywhere from the code. 

**Example:**

```php
<?php
class Employee{
  public $name;
}

$emp1= new Employee();
$emp1->name = 'Harry'; 
?>
```

### Protected

Protected property or method can only be accessed within the class and by the classes derived from that class.

**Example:**

```php
<?php
class ParentClass {
    protected $parentMsg = "protected parent attribute<br>";
    protected function parentDisplay() {
        echo "protected parent method<br>";
        echo $this->parentMsg;
    }
}
class ChildClass extends ParentClass {
    protected $childMsg = "Protected Child attribute.<br>";
    public function childDisplay() {
        echo "Public Child method to display protected parent members:<br>";
        $this->parentDisplay();
    }
}
$child = new ChildClass();
$child->childDisplay();
?>
```

**Output:**

```php
Public Child method to display protected parent members:
protected parent method
protected parent attribute
```

```php
<?php  
class Fruit {  
  public $name;  
  public $color;  
  public function __construct($name, $color) {  
    $this->name = $name;  
    $this->color = $color;  
  }  
  protected function intro() {  
    echo "The fruit is {$this->name} and the color is {$this->color}.";  
  }  
}  
  
class Strawberry extends Fruit {  
  public function message() {  
    echo "Am I a fruit or a berry? ";  
  }  
}  
  
// Try to call all three methods from outside class  
$strawberry = new Strawberry("Strawberry", "red");  // OK. __construct() is public  
$strawberry->message(); // OK. message() is public  
$strawberry->intro(); // ERROR. intro() is protected  
?>
```



### Private

The Private property or method can only be accessed within the class. If it is called outside of the class, then it will throw an error. 

**Example:**

```php
<?php
class Employee {
  public $salary;

  private function set_salary($n) { // a private function
    $this->salary= $n;
  }
}

$emp1= new Employee();
$emp1->set_salary('300'); //It will throw error as It can not Access the Private Function
?>
```

