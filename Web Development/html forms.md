#html  #form #PHP 

Forms enable users to submit data, which can be processed, stored, or returned by a server.

Forms are crucial for tasks such as user authentication, data submission, feedback collection, and more.

### **Sample html form**
```html
 <form action="/submit" method="post">
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
### **Form Control**
The `<input>` tag is commonly used to create form controls. The attributes of this tag define the control's behavior.
- The **"type"** attribute specifies the type of input control (e.g., text, password, checkbox).
- The **"name"** attribute is used for identifying the control, especially when the data is sent to the server.
- The **"value"** attribute sets a default value for the control, which the user can overwrite.

