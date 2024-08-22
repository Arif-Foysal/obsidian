#PHP #superglobal #cookie

<iframe width="560" height="315" src="https://www.youtube.com/embed/SbAfPJj0H4g?si=WYAt878c0MjOsKn8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
### Cookie

Cookie is a small file that the server embeds on the user's computer. Each time the computer opens a webpage, the server will send a cookie to the computer. PHP contains  **setcookie** function to create a cookie object to be sent to the client along with HTTP response.

### Creating Cookies with PHP

A cookie can be created with the **setcookie()** function. 

**Syntax:**

```php
setcookie(name, value, expire, path, domain, secure, httponly);
```
Only the _name_ parameter is required. All other parameters are optional.
>[!Note]
>The `setcookie()` function must appear BEFORE the `<html>` tag.
#### Parameters

- Name − Name of the cookie stored.
- Value − This sets the value of the named variable.
- Expiry − This specifes a future time in seconds since 00:00:00 GMT on 1st Jan 1970.
- Path − Directories for which the cookie is valid.
- Domain − Specifies the domain name in very large domains.
- Security − 1 for HTTPS. Default 0 for regular HTTP.
- httponly - If true, the cookie is only accessible with via http(not JS)

### Example use case of cookie: Remembering user's theme perference

#### **1. Setting the Cookie:**

When a user selects a theme, you can set a cookie to remember their preference.
```php
// Assume the user has selected the dark theme
$theme = "dark";

// Set the cookie to expire in 30 days
setcookie("user_theme", $theme, time() + (86400 * 30), "/");

```

- **`"user_theme"`**: The name of the cookie.
- **`$theme`**: The value, in this case, `"dark"`.
- **`time() + (86400 * 30)`**: The cookie will expire in 30 days (`86400` seconds in a day).
- **`"/"`**: The cookie is available across the entire website.

#### **2. Retrieving the Cookie:**

```php
if (isset($_COOKIE["user_theme"])) {
    $theme = $_COOKIE["user_theme"];
} else {
    // Default to light theme if no cookie is set
    $theme = "light";
}

// Apply the theme to your webpage
echo "The selected theme is: " . $theme;
```

**HTML and php integration**
```php
<?php
// Set the theme based on user selection
if (isset($_POST['theme'])) { 
    $theme = $_POST['theme'];
    setcookie("user_theme", $theme, time() + (86400 * 30), "/");
} elseif (isset($_COOKIE["user_theme"])){ //subsequent visit
    $theme = $_COOKIE["user_theme"];
} else { //initial visit
    $theme = "light"; 
}
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Theme Preference with Cookies</title>
</head>
<body style="background-color: <?php echo ($theme == 'dark') ? '#333' : '#fff'; ?>; color: <?php echo ($theme == 'dark') ? '#fff' : '#000'; ?>;">

    <h1>Welcome to My Website</h1>
    <p>Your current theme is: <?php echo $theme; ?></p>

    <form method="post" action="">
        <label>Select Theme:</label>
        <select name="theme">
            <option value="light" <?php if ($theme == "light") echo "selected"; ?>>Light</option>
            <option value="dark" <?php if ($theme == "dark") echo "selected"; ?>>Dark</option>
        </select>
        <input type="submit" value="Save Preference">
    </form>

</body>
</html>
```

### **How It Works:**

1. **Setting the Theme:**
    - When the user selects a theme and submits the form, a cookie is set with the chosen theme. The cookie expires in 30 days.
2. **Applying the Theme:**
    - On subsequent visits, the script checks for the `user_theme` cookie and applies the stored theme.
    - If the cookie is not set, it defaults to the light theme.


### Modify a cookie value
To modify a cookie, just set (again) the cookie using the `setcookie()` function:
```php
<?php  
$cookie_name = "user";  
$cookie_value = "Alex Porter";  
setcookie($cookie_name, $cookie_value, time() + (86400 * 30), "/");  
?>  
<html>  
<body>  
  
<?php  
if(!isset($_COOKIE[$cookie_name])) {  
  echo "Cookie named '" . $cookie_name . "' is not set!";  
} else {  
  echo "Cookie '" . $cookie_name . "' is set!<br>";  
  echo "Value is: " . $_COOKIE[$cookie_name];  
}  
?>  
  
</body>  
</html>
```

### Delete a cookie
To delete a cookie, use the `setcookie()` function with an expiration date in the past:

```php
<?php  
// set the expiration date to one hour ago  
setcookie("user", "", time() - 3600);  
?>  
<html>  
<body>  
  
<?php  
echo "Cookie 'user' is deleted.";  
?>  
  
</body>  
</html>
```


### Check if Cookies are Enabled

The trick is try to create a test cookie with the `setcookie()` function, then count the `$_COOKIE` array variable:

```php
<?php  
setcookie("test_cookie", "test", time() + 3600, '/');  
?>  
<html>  
<body>  
  
<?php  
if(count($_COOKIE) > 0) {  
  echo "Cookies are enabled.";  
} else {  
  echo "Cookies are disabled.";  
}  
?>  
  
</body>  
</html>
```



- [ ] I'll learn more when i'll need it. #todo 

https://www.w3schools.com/php/php_cookies.asp



