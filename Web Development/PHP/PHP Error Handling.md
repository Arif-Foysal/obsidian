#PHP #webDevelopment 

A good application should always be easily manageable and response to errors in a controlled way.

## Exceptions in PHP
An exception is an **object** that describes an error or unexpected behavior of a PHP script.
An exception is an object that describes an error or unexpected behaviour of a PHP script.

### Throwing an exception
When an exception is thrown, the code following it will not be executed.

**If an exception is not caught, a fatal error will occur with an "Uncaught Exception" message.**

```php
<?php  
function divide($dividend, $divisor) {  
  if($divisor == 0) {  
    throw new Exception("Division by zero");  
  }  
  return $dividend / $divisor;  
}  
  
echo divide(5, 0);  
?>
```
The result will look something like this:

**Fatal error**: **Uncaught Exception**: Division by zero in C:\webfolder\test.php:4  
Stack trace: #0 C:\webfolder\test.php(9):  
divide(5, 0) #1 {main} thrown in **C:\webfolder\test.php** on line **4**

To avoid the error from the example above, we can use the `try...catch` statement to catch exceptions and continue the process.

#### Syntax
```php
try {  
  code that can throw exceptions  
} catch(Exception $e) {  
  code that runs when an exception is caught  
}
```

**Example:**
```php
<?php  
function divide($dividend, $divisor) {
    if ($divisor == 0) {
        throw new Exception("Division by zero");
    }
    return $dividend / $divisor;
}

try {
    echo divide(10, 2); // Outputs: 5
    echo "<br>";
    echo divide(10, 0); // Triggers an exception
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
}
?>
```

#### **Explanation:**

- **`throw`**: Used to throw an exception when a specific error condition occurs.
- **`try`**: Wraps the code that might throw an exception.
- **`catch`**: Captures and handles the exception thrown by the code in the `try` block.

### The Exception object
The Exception Object contains information about the error or unexpected behaviour that the function encountered.
`syntax`
```
new Exception(message, code, previous)
```

### Parameter Values

| Parameter | Description                                                                                                                                |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| message   | Optional. A string describing why the exception was thrown                                                                                 |
| code      | Optional. An integer that can be used to easily distinguish this exception from others of the same type                                    |
| previous  | Optional. If this exception was thrown in a catch block of another exception, it is recommended to pass that exception into this parameter |
### Methods

When catching an exception, the following table shows some of the methods that can be used to get information about the exception:

| Method        | Description                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------------- |
| getMessage()  | Returns a string describing why the exception was thrown                                                                   |
| getPrevious() | If this exception was triggered by another one, this method returns the previous exception. If not, then it returns _null_ |
| getCode()     | Returns the exception code                                                                                                 |
| getFile()     | Returns the full path of the file in which the exception was thrown                                                        |
| getLine()     | Returns the line number of the line of code which threw the exception                                                      |
**Example:**
```php
<?php  
function divide($dividend, $divisor) {  
  if($divisor == 0) {  
    throw new Exception("Division by zero", 1);  
  }  
  return $dividend / $divisor;  
}  
  
try {  
  echo divide(5, 0);  
} catch(Exception $ex) {  
  $code = $ex->getCode();  
  $message = $ex->getMessage();  
  $file = $ex->getFile();  
  $line = $ex->getLine();  
  echo "Exception thrown in $file on line $line: [Code $code]  
  $message";  
}  
?>
```


### Custom Exception classes
You can create custom exception classes by extending the built-in `Exception` class. This allows you to define exceptions specific to your application's needs.
```php
class CustomException extends Exception {
    public function errorMessage() {
        // Error message
        return "Error on line {$this->getLine()} in {$this->getFile()}: {$this->getMessage()}";
    }
}

try {
    throw new CustomException("A custom error occurred.");
} catch (CustomException $e) {
    echo $e->errorMessage();
}
```

`result`
```
Error on line 14 in /home/MQnzaK/prog.php: A custom error occurred.
```

#### **Explanation:**

- **`CustomException`** extends the `Exception` class, allowing you to add custom behavior or messages.
- **`errorMessage()`**: A method in the custom exception class that provides a custom error message format.

## Handling multiple exceptions
You can catch different types of exceptions by using multiple `catch` blocks.

```php
class DivideByZeroException extends Exception {}
class NegativeNumberException extends Exception {}

function checkNumber($number) {
    if ($number == 0) {
        throw new DivideByZeroException("Cannot divide by zero");
    }
    if ($number < 0) {
        throw new NegativeNumberException("Negative numbers are not allowed");
    }
    return true;
}

try {
    checkNumber(-5);
} catch (DivideByZeroException $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
} catch (NegativeNumberException $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
}
```

## Finally Block
The `finally` block can be used to execute code regardless of whether an exception is thrown or not.

```php
try {  
  //code that can throw exceptions  
} catch(Exception $e) {  
  //code that runs when an exception is caught  
} finally {  
  //code that always runs regardless of whether an exception was caught  
}
```

```php
try {
    echo divide(10, 0);
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
} finally {
    echo "This will always be executed.";
}
```

# Logging errors in PHP

<iframe width="560" height="315" src="https://www.youtube.com/embed/EoP5PqvoLHg?si=ceFu_wPSFYT6bXcl" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

It is a good practice to log errors for debugging purposes. PHP allows you to log errors using the `error_log()` function.

```php
error_log("A custom error occurred.", 3, "/var/log/php_errors.log");
```



# **Scenario: Processing a configuration file**

Imagine you have a PHP script that reads a configuration file (`config.json`) containing critical settings for your application. The script needs to:

1. **Open the file**.
2. **Read and decode the JSON data**.
3. **Process the data** (e.g., validating settings).
4. **Close the file** after processing, whether the process was successful or not.

If an error occurs at any step (like if the file doesn’t exist, the JSON is malformed, or the data is invalid), the script should catch the error, handle it appropriately, and still ensure that the file is closed properly.

```php
<?php

function processConfigFile($filename) {
    $file = null;

    try {
        // Attempt to open the file
        $file = fopen($filename, 'r');
        if (!$file) {
            throw new Exception("Unable to open file: $filename");
        }

        // Read the file contents
        $content = fread($file, filesize($filename));
        if ($content === false) {
            throw new Exception("Failed to read file: $filename");
        }

        // Decode the JSON data
        $config = json_decode($content, true);
        if (json_last_error() !== JSON_ERROR_NONE) {
            throw new Exception("Invalid JSON in file: $filename");
        }

        // Process the configuration (e.g., validate settings)
        if (!isset($config['setting1']) || !isset($config['setting2'])) {
            throw new Exception("Required settings are missing in the configuration file.");
        }

        echo "Configuration processed successfully.";

    } catch (Exception $e) {
        // Handle any exceptions that occurred
        echo 'Error: ', $e->getMessage(), "\n";
    } finally {
        // Ensure the file is closed, even if an error occurred
        if ($file) {
            fclose($file);
            echo "File closed.\n";
        }
    }
}

// Example usage
processConfigFile('config.json');
?>
```

### **Explanation:**

1. **`try` Block:**
    
    - The `try` block contains all the operations that might throw exceptions. It attempts to open the file, read its contents, decode the JSON, and validate the data.
2. **`catch` Block:**
    
    - If any error occurs during the operations inside the `try` block, an exception is thrown. The `catch` block captures this exception and handles it by printing an error message.
3. **`finally` Block:**
    
    - The `finally` block runs regardless of whether an exception was thrown or not. It ensures that the file is always closed, preventing resource leaks, which is especially important in file handling.

### **More Real-World Application:**

This pattern is useful in many real-world scenarios, such as:

- **Database Operations:** Ensuring a database connection is always closed after executing queries, even if an error occurs.
- **External API Calls:** Handling potential failures when calling an external API and ensuring any resources (e.g., sockets) are properly closed.
- **Transaction Management:** In a system that uses transactions, ensuring that a transaction is either committed or rolled back correctly.

### 1. **Database Transactions**

When performing multiple database operations that should be treated as a single unit, you can use transactions. If any operation within the transaction fails, you need to roll back the transaction to ensure the database remains consistent.

#### **Scenario:**

Suppose you're creating a new order in an e-commerce application. You need to insert the order details into the `orders` table, update the `inventory` table to decrease stock, and log the transaction.

#### **Code Example:**

```php
<?php

function createOrder($orderDetails) {
    $db = new PDO('mysql:host=localhost;dbname=ecommerce', 'user', 'password');

    try {
        // Start transaction
        $db->beginTransaction();

        // Insert order details
        $stmt = $db->prepare("INSERT INTO orders (user_id, product_id, quantity) VALUES (?, ?, ?)");
        $stmt->execute([$orderDetails['user_id'], $orderDetails['product_id'], $orderDetails['quantity']]);

        // Update inventory
        $stmt = $db->prepare("UPDATE inventory SET stock = stock - ? WHERE product_id = ?");
        $stmt->execute([$orderDetails['quantity'], $orderDetails['product_id']]);

        // Log the transaction
        $stmt = $db->prepare("INSERT INTO logs (user_id, action) VALUES (?, ?)");
        $stmt->execute([$orderDetails['user_id'], 'Created order']);

        // Commit transaction
        $db->commit();
        echo "Order created successfully.";
    } catch (Exception $e) {
        // Rollback transaction on error
        $db->rollBack();
        echo "Failed to create order: " . $e->getMessage();
    } finally {
        // Close the database connection
        $db = null;
    }
}

// Example usage
$orderDetails = ['user_id' => 1, 'product_id' => 2, 'quantity' => 3];
createOrder($orderDetails);

?>
```
### 2. **File Upload Handling**

When uploading files to a server, you might need to perform several operations like validating the file, moving it to a specific directory, and updating a database with the file details. If any of these steps fail, you need to clean up by deleting the partially uploaded file or rolling back database changes.

#### **Scenario:**

You're building a profile picture upload feature. You need to validate the uploaded image, move it to the `uploads` directory, and update the user's profile in the database.

#### **Code Example:**
```php
<?php

function uploadProfilePicture($file, $userId) {
    $uploadDir = 'uploads/';
    $uploadFile = $uploadDir . basename($file['name']);
    
    try {
        // Check if file is a valid image
        if (!getimagesize($file['tmp_name'])) {
            throw new Exception("File is not an image.");
        }

        // Attempt to move the uploaded file
        if (!move_uploaded_file($file['tmp_name'], $uploadFile)) {
            throw new Exception("Failed to move uploaded file.");
        }

        // Update user's profile picture in the database
        $db = new PDO('mysql:host=localhost;dbname=myapp', 'user', 'password');
        $stmt = $db->prepare("UPDATE users SET profile_picture = ? WHERE id = ?");
        $stmt->execute([$uploadFile, $userId]);

        echo "Profile picture uploaded successfully.";
    } catch (Exception $e) {
        echo "Failed to upload profile picture: " . $e->getMessage();
    } finally {
        // Perform any necessary cleanup, such as deleting an incomplete file
        if (file_exists($uploadFile) && !isset($db)) {
            unlink($uploadFile);
        }
    }
}

// Example usage
uploadProfilePicture($_FILES['profile_picture'], 1);

?>
```
### 3. **External API Calls**

When making calls to an external API, there are many points of failure, such as network issues, timeouts, or unexpected responses. You want to handle these gracefully and ensure that any resources (like a cURL session) are cleaned up properly.

#### **Scenario:**

You have a script that fetches weather data from an external API and stores it in your database.

#### **Code Example:**
```php
<?php

function fetchWeatherData($city) {
    $apiUrl = "http://api.weather.com/v3/wx/conditions/current?city=" . urlencode($city);
    $ch = curl_init();

    try {
        // Set up the cURL options
        curl_setopt($ch, CURLOPT_URL, $apiUrl);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);

        // Execute the API call
        $response = curl_exec($ch);
        if (curl_errno($ch)) {
            throw new Exception("cURL error: " . curl_error($ch));
        }

        // Decode the JSON response
        $data = json_decode($response, true);
        if (json_last_error() !== JSON_ERROR_NONE) {
            throw new Exception("Invalid JSON response");
        }

        // Process and store the data in the database
        $db = new PDO('mysql:host=localhost;dbname=weather_app', 'user', 'password');
        $stmt = $db->prepare("INSERT INTO weather (city, temperature, conditions) VALUES (?, ?, ?)");
        $stmt->execute([$city, $data['temperature'], $data['conditions']]);

        echo "Weather data fetched and stored successfully.";
    } catch (Exception $e) {
        echo "Failed to fetch weather data: " . $e->getMessage();
    } finally {
        // Close the cURL session and the database connection
        curl_close($ch);
        $db = null;
    }
}

// Example usage
fetchWeatherData("New York");

?>
```

### 4. **Resource Management**

When working with any kind of resource, such as a connection to a third-party service, an open file handle, or a session, you need to ensure that the resource is properly released or closed, even if an error occurs during its usage.

#### **Scenario:**

You are interacting with an external messaging service to send out notifications. You need to ensure that the connection to the service is always closed, regardless of whether the message was successfully sent.

#### **Code Example:**

```php
<?php

function sendMessage($message, $recipient) {
    $serviceConnection = null;

    try {
        // Connect to the messaging service
        $serviceConnection = new MessagingService();
        $serviceConnection->connect();

        // Send the message
        $serviceConnection->send($recipient, $message);
        echo "Message sent successfully.";

    } catch (Exception $e) {
        echo "Failed to send message: " . $e->getMessage();

    } finally {
        // Ensure the service connection is closed
        if ($serviceConnection) {
            $serviceConnection->disconnect();
            echo "Service connection closed.";
        }
    }
}

// Example usage
sendMessage("Hello, World!", "+1234567890");

?>
```

### 5. **Session Management**

When working with sessions, especially in a multi-step process (like a checkout process), you may need to ensure that sessions are properly started, used, and closed or destroyed, regardless of errors.

#### **Scenario:**

You are building a checkout process where user details are stored in a session. If something goes wrong, you want to ensure the session is properly closed or cleared.

#### **Code Example:**
```php
<?php

function checkout() {
    session_start();

    try {
        // Assume $_SESSION['cart'] has the items to be purchased
        if (!isset($_SESSION['cart'])) {
            throw new Exception("Cart is empty.");
        }

        // Process the checkout (e.g., deduct from inventory, charge payment, etc.)
        processOrder($_SESSION['cart']);

        // Clear the cart after successful checkout
        $_SESSION['cart'] = [];
        echo "Checkout completed successfully.";

    } catch (Exception $e) {
        echo "Checkout failed: " . $e->getMessage();

    } finally {
        // Ensure the session is properly closed
        session_write_close();
    }
}

// Example usage
checkout();
?>
```
