#PHP #webDevelopment #file

[[PHP Strings]]
### Opening a File

To open a file in PHP, you use the `fopen()` function. This function takes two main parameters: the file name and the mode in which you want to open the file.

#### Modes:

- **`r`** : Open in read mode. File pointer starts at the beginning of the file.
- **`w`** : Open in write mode. Erases the contents of the file or creates a new file if it doesn’t exist.
- **`a`** : Open for write only. ile pointer starts at the end of the file. Creates a new file if the file doesn't exist.
- **`x`** : **Creates a new file for write only**. Returns FALSE and an error if file already exists.
- **`r+`** : **Open a file for read/write**. File pointer starts at the beginning of the file
- **`w+`** : **Open a file for read/write**. Erases the contents of the file or creates a new file if it doesn't exist. File pointer starts at the beginning of the file.
- **`a+`** : **Open a file for read/write**. The existing data in file is preserved. File pointer starts at the end of the file. Creates a new file if the file doesn't exist
- **`x+`** : **Creates a new file for read/write**. Returns FALSE and an error if file already exists.
#### Example:

```php
<?php
$file = fopen("example.txt", "r"); // Open a file for reading
if ($file) {
    // Perform file operations
    fclose($file); // Close the file when done
} else {
    echo "Error opening file.";
}
?>
```

### Reading a File
PHP provides several functions to read the contents of a file.

- **`fread()`**: Reads a specified number of bytes from a file.
- **`fgets()`**: Reads a single line from a file.
- **`file_get_contents()`**: Reads the entire file into a string.
- **`readfile()`**: Reads a file and writes it to the output buffer.
#### The `readfile()` function:
If all you want to do is to read a file's content, you use `readfile()` function:
```php
<?php  
echo readfile("newtext.txt");  
?>
```

But, a better practice is to properly opening a file and using the `fread()` function:
#### The `fread()` function:
The `fread()` function reads from an open file.
**parameters:**
- The first parameter of `fread()` contains the name of the file to read from and 
- The second parameter specifies the maximum number of bytes to read.

```php
$a = fopen("test.txt", "r");
echo fread($a, filesize("test.txt"));
```

#### Read single line `fgets()`:
The `fgets()` function is used to read a single line from a file.

Outputting the first line of `webdictionary.txt`:
```php
<?php  
$myfile = fopen("webdictionary.txt", "r") or die("Unable to open file!");  
echo fgets($myfile);  
fclose($myfile);  
?>
```

>[!Important Note] 
>**Each call to `fgets($file)` reads the next line from the file and returns it as a string.**

Reading the whole file by iteration:
```php
<?php
$file = fopen("example.txt", "r");
if ($file) {
    while (($line = fgets($file)) !== false) {
        echo $line; // Output each line
    }
    fclose($file);
} else {
    echo "Error opening file.";
}
?>
```

Another approach to check the end of file is to use `feof()`
#### PHP Check End-Of-File - `feof()`
The `feof()` function is useful for looping through data of unknown length.

```php
<?php  
$myfile = fopen("webdictionary.txt", "r") or die("Unable to open file!");  
// Output one line until end-of-file  
while(!feof($myfile)) {  
  echo fgets($myfile) . "<br>";  
}  
fclose($myfile);  
?>
```
#### ## PHP Read Single Character - `fgetc()`
```php
<?php  
$myfile = fopen("webdictionary.txt", "r") or die("Unable to open file!");  
// Output one character until end-of-file  
while(!feof($myfile)) {  
  echo fgetc($myfile);  
}  
fclose($myfile);  
?>
```

### Writing to a file

#### Creating new file
`fopen()` is also used create files if opened with certain modes [[PHP File Handling#Modes]].
```php
$myfile = fopen("testfile.txt", "w");//creates new file if testfile.txt does not exist
```

You can write data to a file using functions like `fwrite()` or `file_put_contents()`.

- **`fwrite()`**: Writes a string to a file.
- **`file_put_contents()`**: Writes data to a file, and can optionally lock the file or append data.

>[!Note] 
>Make sure you have OS level permission for the web-server on the directory you want to write to.

#### write to a file `fwrite()`
used to write on a file.
**Parameters:**
- First param contains the name of the file to write.
- Second one contains the string to be written.

**Example:**
```php
$myfile = fopen("one.txt","w");
fwrite($myfile, "You have been caught!!!");
```

>[!Warning]
>If you write on a file opened in `w` mode, you will basically overwrite to the file and lose the previous data.
#### Append to a file
You open the file with `a` (append) mode and then write to the file.

```php
$myfile = fopen("text.txt", "a");
$txt = "one<br>";
$txt = "two";
readfile("text.txt");
```
Output:
```
one
two
```


### PHP file upload

#### configuring `php.ini` file
Uploading files to the server requires configuring the `php.ini` file.
- **To locate php.ini file:**
```php
<?php
phpinfo();
?>
```
- **Turn on file_uploads:**
In your "php.ini" file, search for the `file_uploads` directive, and set it to On:
```php
file_uploads = On
```

- **Some Directives that you might also want to change in `php.ini` file**
	- **`upload_max_filesize`:** This controls the maximum size of a file that can be uploaded.
    
    ini
    
    Copy code
    
    `upload_max_filesize = 2M`
    
    Adjust `2M` to the maximum file size you want to allow (e.g., `10M` for 10 megabytes).
    
	- **`post_max_size`:** This controls the maximum size of POST data that PHP will accept, which includes all uploaded files.
	    
	    ini
	    
	    Copy code
	    
	    `post_max_size = 8M`
	    
	    Ensure this value is larger than `upload_max_filesize`.
	    
	- **`max_file_uploads`:** This controls the maximum number of files that can be uploaded simultaneously.
	    
	    ini
	    
	    Copy code
	    
	    `max_file_uploads = 20`

#### Upload file php script

`upload.php`
```php
<?php

if ($_SERVER['REQUEST_METHOD'] === 'POST') {

// Directory where files will be uploaded
$targetDir = "uploads/";

// The path of the file to be uploaded
$targetFile = $targetDir . basename($_FILES["image"]["name"]);

// Variable to store upload status
$uploadOk = 1;

// Check if the file is an actual image or a fake image
$check = getimagesize($_FILES["image"]["tmp_name"]);

if ($check !== false) {
echo "File is an image - " . $check["mime"] . ".<br>";
$uploadOk = 1;
} else {
echo "File is not an image.<br>";
$uploadOk = 0;
}

// Check if file already exists

if (file_exists($targetFile)) {
echo "Sorry, file already exists.<br>";
$uploadOk = 0;
}

// Check file size (limit: 2MB)

if ($_FILES["image"]["size"] > 2000000) {
echo "Sorry, your file is too large.<br>";
$uploadOk = 0;
}

// Allow certain file formats
$imageFileType = strtolower(pathinfo($targetFile, PATHINFO_EXTENSION));

if ($imageFileType != "jpg" && $imageFileType != "png" && $imageFileType != "jpeg" && $imageFileType != "gif") {

echo "Sorry, only JPG, JPEG, PNG & GIF files are allowed.<br>";

$uploadOk = 0;

}

// Check if $uploadOk is set to 0 by an error

if ($uploadOk == 0) {

echo "Sorry, your file was not uploaded.<br>";

} else {

// Try to upload file

if (move_uploaded_file($_FILES["image"]["tmp_name"], $targetFile)) {

echo "The file " . htmlspecialchars(basename($_FILES["image"]["name"])) . " has been uploaded.";

} else {

echo "Sorry, there was an error uploading your file.<br>";

}

}

}

?>

  

<!-- HTML form to upload the image -->

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Upload Image</title>
</head>
<body>
<h2>Upload an Image</h2>
<form action="#" method="post" enctype="multipart/form-data">
Select image to upload:
<input type="file" name="image" id="image">
<input type="submit" value="Upload Image" name="submit">
</form>
</body>
</html>
```

