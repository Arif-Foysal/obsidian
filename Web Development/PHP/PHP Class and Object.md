#PHP #oop 

>[[PHP Inheritance]]
### **Class**

**Syntax:**

```php
<?php
class class_name {
  // code goes here...
}
?>
```


**Example:**
We will create a class **Employee** where we will have two properties and two methods for setting and getting the property.

```php
<?php
class Employee {
  // Properties
  public $name;
  public $surname;

  // Methods
  function set_name($name) {
    $this->name = $name;
  }
  function get_name() {
    return $this->name;
  }
}
?>
```

**Note: The $this keyword refers to the current object, and is only available inside methods.**

### **Object**
**Syntax:**
```php
$object_name = new ClassName();
```

### **Creating an Object in PHP**

We will create two objects in the following example. 

```php
<?php
class Employee {
  // Properties
  public $name;
  public $surname;

  // Methods
  function set_name($name) {
    $this->name = $name;
  }
  function get_name() {
    return $this->name;
  }
}

$emp1 = new Employee();
$emp2= new Employee();
$emp1->set_name('Harry');
$emp2->set_name('Shayan');

echo $emp1->get_name();
echo "<br>";
echo $emp2->get_name();
?>
```

**Output:**

```php
Harry
Shayan
```