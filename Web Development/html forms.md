#html  #form #PHP 

Forms enable users to submit data, which can be processed, stored, or returned by a server.

Forms are crucial for tasks such as user authentication, data submission, feedback collection, and more.

### **Sample html form**
```html
 <form action="process_form.php" method="post">
    <!-- Text input for username -->
    <label for="username">Username:</label>
    <input type="text" id="username" name="username" required>
    <br><br>

    <!-- Password input -->
    <label for="password">Password:</label>
    <input type="password" id="password" name="password" required>
    <br><br>

    <!-- Radio buttons for gender -->
    <label>Gender:</label>
    <input type="radio" id="male" name="gender" value="male">
    <label for="male">Male</label>
    <input type="radio" id="female" name="gender" value="female">
    <label for="female">Female</label>
    <br><br>
    <!-- Submit button -->
    <input type="submit" value="Submit">
  </form>
```
- The `method="post"` attribute specifies that the form data should be sent using the POST method.
- The `action="process_form.php"` attribute specifies the file (`process_form.php`) that will handle the form submission.

### **Form Control**
The `<input>` tag is commonly used to create form controls. The attributes of this tag define the control's behavior.
- The **"type"** attribute specifies the type of input control (e.g., text, password, checkbox).
- The **"name"** attribute is used for identifying the control, especially when the data is sent to the server.
- The **"value"** attribute sets a default value for the control, which the user can overwrite.

### `ecntype` attribute in form
[[PHP File Handling#PHP file upload]]
The `enctype` attribute specifies how the form-data should be encoded when submitting it to the server.
**Attribute Values:**

| Value                             | Description                                                                                                                                     |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| application/x-www-form-urlencoded | Default. All characters are encoded before sent (spaces are converted to "+" symbols, and special characters are converted to ASCII HEX values) |
| multipart/form-data               | This value is necessary if the user will upload a file through the form                                                                         |
| text/plain                        | Sends data without any encoding at all. Not recommended                                                                                         |




