#PHP #oop 

### Constructor

In PHP, a constructor allows you to initialize an object's properties upon the creation of the object. The constructor function starts with two underscores (`__`) and if we create a `__construct()` function, then PHP will automatically call this function when we create an object from a class. 

**Example:**

```php
<?php
class Employee {
  public $name;
  public $surname;

  function __construct($name) {
    $this->name = $name;
  }
  function get_name() {
    return $this->name;
  }
}
$emp1= new Employee("Lovish");
echo $emp1->get_name();
?>
```

**Output:**

```php
Lovish
```

### Destructor

A destructor is called when the object is destructed or the script is **stopped** or **exited**.
 The Destructor function starts with two underscores (`__`) and if we create a `__destruct()` function, then PHP will automatically call this function at the end of the script. 

The purpose of a destructor is to clean up any resources that the object may have been holding, such as closing database connections, freeing memory, or writing data to logs before the object is removed from memory.

**Example:**

```php
<?php
class Employee {
  public $name;

  function __construct($name) {
    $this->name = $name;
  }
  function __destruct() {
    echo "Employee name is {$this->name}.";
  }
}

$emp1= new Employee("Izhaan");
?>
```

**Output:**

```php
Employee name is Izhaan.
```

#### **When is the Destructor called:**
- **End of Script Execution:** The destructor is automatically called when the script execution ends.
- **Explicit Object Destruction:** If an object is explicitly destroyed using `unset()`, the destructor is called immediately.


### Use case example of destructor

```php
<?php

class FileHandler {
    private $fileHandle;

    public function __construct($filename) {
        $this->fileHandle = fopen($filename, 'w');
        if ($this->fileHandle) {
            echo "File opened successfully.\n";
        } else {
            echo "Failed to open file.\n";
        }
    }

    public function writeData($data) {
        if ($this->fileHandle) {
            fwrite($this->fileHandle, $data);
        }
    }

    public function __destruct() {
        if ($this->fileHandle) {
            fclose($this->fileHandle);
            echo "File closed successfully.\n";
        }
    }
}

$fileHandler = new FileHandler("example.txt");
$fileHandler->writeData("This is a sample text.\n");

// Destructor is automatically called at the end of the script, closing the file.
?>
```


