#PHP #JSON

[[JSON]]

### **Key JSON Functions in PHP**

PHP provides several built-in functions for working with JSON data:

- **`json_encode()`**: Converts a PHP variable (such as an array or object) into a JSON string.
- **`json_decode()`**: Converts a JSON string into a PHP variable (such as an array or object).

## **`json_encode()`: Encoding php data to json**

```php
$data = [
    "name" => "John Doe",
    "email" => "john@example.com",
    "age" => 28,
    "is_active" => true
];

$jsonData = json_encode($data);

echo $jsonData;
```

`output`
```php
{"name":"John Doe","email":"john@example.com","age":28,"is_active":true}
```
The associative array `$data` is converted to a JSON string using `json_encode()`.

## **`json_decode()` Decoding json  to php data**
used to convert [[JSON]] string back into a php variable

```php
$jsonData = '{"name":"John Doe","email":"john@example.com","age":28,"is_active":true}';

$data = json_decode($jsonData, true); // Passing true returns an associative array

print_r($data);
```

`output`
```php
Array
(
    [name] => John Doe
    [email] => john@example.com
    [age] => 28
    [is_active] => 1
)
```

**Explanation:**
- The JSON string `$jsonData` is converted back into a PHP associative array using `json_decode()`.
- The `true` parameter specifies that the JSON should be decoded into an associative array instead of an object.
## **Encoding an object**
```php
class User {
    public $name;
    public $email;
    public $age;
    public $is_active;

	    public function __construct($name, $email, $age, $is_active) {
        $this->name = $name;
        $this->email = $email;
        $this->age = $age;
        $this->is_active = $is_active;
    }
}

$user = new User("Jane Doe", "jane@example.com", 30, true);

$jsonData = json_encode($user);

echo $jsonData;
```

`output`
```php
{"name":"Jane Doe","email":"jane@example.com","age":30,"is_active":true}
```

## **Decoding JSON to php object**
```php
$jsonData = '{"name":"Jane Doe","email":"jane@example.com","age":30,"is_active":true}';

$user = json_decode($jsonData); // Decodes into a PHP object

echo $user->name; // Outputs: Jane Doe

```

## **Handling JSON errors**
If something goes wrong during encoding or decoding, you can use `json_last_error()` and `json_last_error_msg()` to get more information about the error.
```php
$invalidJson = "{'name': 'Invalid JSON'}"; // JSON should use double quotes

$data = json_decode($invalidJson);

if (json_last_error() !== JSON_ERROR_NONE) {
    echo "JSON Error: " . json_last_error_msg();
}
```

`output`
```
JSON Error: Syntax error
```

## **Use Case: Sending Data in JSON Format**
- [ ] Learn more about [[RESTful API]] #todo 

Let’s say you are building a [[RESTful API]]. You might send data from the server to the client in JSON format.

```php
header('Content-Type: application/json');

$response = [
    "status" => "success",
    "message" => "Data retrieved successfully",
    "data" => [
        "name" => "John Doe",
        "email" => "john@example.com"
    ]
];

echo json_encode($response);
```

The server would send the following JSON response to the client:
`output`
```php
{
    "status": "success",
    "message": "Data retrieved successfully",
    "data": {
        "name": "John Doe",
        "email": "john@example.com"
    }
}
```


## **Common JSON options**

- **`JSON_PRETTY_PRINT`**: Formats the JSON string to be more human-readable with indentation and newlines.
- **`JSON_UNESCAPED_SLASHES`**: Prevents escaping of slashes.
- **`JSON_UNESCAPED_UNICODE`**: Prevents escaping of Unicode characters.

```php
$data = [
    "name" => "John Doe",
    "website" => "https://example.com",
    "bio" => "I ❤️ coding!"
];

$jsonData = json_encode($data, JSON_PRETTY_PRINT | JSON_UNESCAPED_SLASHES | JSON_UNESCAPED_UNICODE);

echo $jsonData;
```

`output`
```php
{
    "name": "John Doe",
    "website": "https://example.com",
    "bio": "I ❤️ coding!"
}
```

>[!Tips]
>There are more interesting parameters of json_encode() and json_decode() functions. You might want to learn them later.

## json_encode() parameters

```php
json_encode(mixed $value, int $flags = 0, int $depth = 512): string|false
```

#### **Parameters:**
1. **`$value`** (mixed):
    - The value to be encoded into JSON format. This can be any type of PHP data, including arrays, objects, strings, numbers, and more.
	    ```php
	    $data = ["name" => "John", "age" => 30];
		```
2. **`$flags`** (int):
   Optional. A bitmask of JSON encode options. You can combine multiple flags using the bitwise OR (`|`) operator. The default is `0`, meaning no special options are used.
   **Common Flags:**	
	- **`JSON_HEX_TAG`**: Encodes `<` and `>` as `\u003C` and `\u003E`.
	- **`JSON_HEX_AMP`**: Encodes `&` as `\u0026`.
	- **`JSON_HEX_APOS`**: Encodes `'` as `\u0027`.
	- **`JSON_HEX_QUOT`**: Encodes `"` as `\u0022`.
	- **`JSON_FORCE_OBJECT`**: Outputs an object instead of an array when the value is an empty array.
	- **`JSON_NUMERIC_CHECK`**: Encodes numeric strings as numbers.
	- **`JSON_PRETTY_PRINT`**: Formats the JSON string with spaces and indentation to make it more human-readable.
	- **`JSON_UNESCAPED_SLASHES`**: Prevents escaping of slashes (`/`).
	- **`JSON_UNESCAPED_UNICODE`**: Prevents escaping of Unicode characters.
	- **`JSON_PARTIAL_OUTPUT_ON_ERROR`**: Outputs partial JSON data if an encoding error occurs.
	- **`JSON_THROW_ON_ERROR`**: Throws a `JsonException` on encoding errors.
3. **`$depth`** (int):
	Optional. The maximum depth of the structure being encoded. The default is `512`. If the structure exceeds this depth, `json_encode()` will return `false`.
	```php
	$json = json_encode($nestedArray, 0, 10); // Limits encoding to 10 levels deep
	```

#### Return Value
- Returns a JSON encoded string on success or `false` on failure.



- [ ] read and format the below part later #todo


### **2. `json_decode()` Parameters**

php

Copy code

`json_decode(string $json, bool $assoc = false, int $depth = 512, int $flags = 0): mixed`

#### **Parameters:**

1. **`$json`** (string):
    
    - The JSON string to be decoded. This must be a valid JSON string.
    - **Example:**
        
        php
        
        Copy code
        
        `$jsonString = '{"name": "John", "age": 30}';`
        
2. **`$assoc`** (bool):
    
    - Optional. When `true`, the returned object will be converted into an associative array. When `false` (the default), the JSON objects will be returned as `stdClass` objects.
    - **Example:**
        
        php
        
        Copy code
        
        `$array = json_decode($jsonString, true); // Decodes to an associative array $object = json_decode($jsonString, false); // Decodes to an object`
        
3. **`$depth`** (int):
    
    - Optional. The maximum depth of the structure being decoded. The default is `512`. If the structure exceeds this depth, `json_decode()` will return `null`.
    - **Example:**
        
        php
        
        Copy code
        
        `$data = json_decode($deepJsonString, true, 10); // Limits decoding to 10 levels deep`
        
4. **`$flags`** (int):
    
    - Optional. A bitmask of JSON decode options. The default is `0`, meaning no special options are used.
        
    - **Common Flags:**
        
        - **`JSON_BIGINT_AS_STRING`**: Decodes large integers as strings instead of numbers, to avoid precision loss.
        - **`JSON_OBJECT_AS_ARRAY`**: Forces JSON objects to be decoded as associative arrays.
        - **`JSON_THROW_ON_ERROR`**: Throws a `JsonException` on decoding errors.
    - **Example:**
        
        php
        
        Copy code
        
        `$data = json_decode($jsonString, true, 512, JSON_BIGINT_AS_STRING);`
        

#### **Return Value:**

- Returns the value encoded in `json` in appropriate PHP data types (`array`, `object`, `string`, `int`, etc.).
- Returns `null` if the JSON cannot be decoded or if the depth is deeper than the given `depth` parameter.

### **Example of Using Both Functions with Parameters**

php

Copy code

`$data = [     "name" => "John",     "website" => "https://example.com",     "bio" => "I ❤️ coding!" ];  // Encode with pretty print and unescaped slashes $json = json_encode($data, JSON_PRETTY_PRINT | JSON_UNESCAPED_SLASHES); echo $json;  // Decode the JSON into an associative array $decodedData = json_decode($json, true, 512, JSON_THROW_ON_ERROR); print_r($decodedData);`