#html 

When you move the mouse over a link, the mouse arrow will turn into a little hand.

>[!Note:] 
>A link does not have to be text. A link can be an image or any other HTML element!

### **In a Nutshell**
- Use the `<a>` element to define a link
- Use the `href` attribute to define the link address
- Use the `target` attribute to define where to open the linked document
- Use the `<img>` element (inside `<a>`) to use an image as a link
- Use the `mailto:` scheme inside the `href` attribute to create a link that opens the user's email program




The HTML `<a>` tag defines a hyperlink. It has the following syntax:
```html
<a href="_url_">_link text_</a>
```

#### **The Target Attribute**
The `target` attribute specifies where to open the linked document.

**Target Attribute Values:**
- `_self` - Default. Opens the document in the same window/tab as it was clicked
- `_blank` - Opens the document in a new window or tab
- `_parent` - Opens the document in the parent frame
- `_top` - Opens the document in the full body of the window

#### **Absolute URLs vs. Relative URLs**

Both examples above are using an **absolute URL** (a full web address) in the `href` attribute.

A local link (a link to a page within the same website) is specified with a **relative URL** (without the "https://www" part):

##### **Example**
**Absolute URLs**
```
<p><a href="https://www.w3.org/">W3C</a></p>  
<p><a href="https://www.google.com/">Google</a></p>  
```

**Relative URLs**
```
<p><a href="html_images.asp">HTML Images</a></p>  
<p><a href="/css/default.asp">CSS Tutorial</a></p>
```


#### **Using an Image as a link:**

```html
<a href="default.asp">  
<img src="smiley.gif" alt="HTML tutorial" style="width:42px;height:42px;">  
</a>
```

#### **Link to an Email Address**
Use `mailto:` inside the `href` attribute to create a link that opens the user's email program (to let them send a new email):
##### Example
`<a href="mailto:someone@example.com">Send email</a>`
**Output:**
<a href="mailto:someone@example.com">Send email</a>

#### **Link to a specific part of web page**
When the link is clicked, the page will scroll down or up to the location with the bookmark/heading.
First, use the `id` attribute to create a bookmark:
`<h2 id="C4">Chapter 4</h2>`

Then, add a link to the bookmark/heading ("Jump to Chapter 4"), from within the same page:
`<a href="#C4">Jump to Chapter 4</a>`



#### **Button as a Link:**
>[[html buttons]]

To use an HTML button as a link, you have to add some JavaScript code.

JavaScript allows you to specify what happens at certain events, such as a click of a button:
```html
<button onclick="document.location='default.asp'">HTML Tutorial</button>
```

#### **Link as a button:**
Links can be styles as a button by using [[CSS]].

```css
<style>  
a:link, a:visited {  background-color: #f44336;  
  color: white;  
  padding: 15px 25px;  
  text-align: center;  
  text-decoration: none;  
  display: inline-block;}  
  
a:hover, a:active {  background-color: red;}  
</style>
```


#### **Link Titles**
The information is most often shown as a tooltip text when the mouse moves over the element.
```html
<a href="https://www.w3schools.com/html/" title="Go to W3Schools HTML section">Visit our HTML Tutorial</a>
```
**Output:**
<a href="https://www.w3schools.com/html/" title="Go to W3Schools HTML section">Visit our HTML Tutorial</a>

### **Link Colors**
By default, a link will appear like this (in all browsers):

- An unvisited link is underlined and blue
- A visited link is underlined and purple
- An active link is underlined and red

You can change the link state colors, by using CSS :

```css
<style>  
a:link {  color: green;  
  background-color: transparent;  
  text-decoration: none;}  
  <!--removes the underline -->
  
a:visited {  color: pink;  
  background-color: transparent;  
  text-decoration: none;}  
  
a:hover {  color: red;  
  background-color: transparent;  
  text-decoration: underline;}  
  
a:active {  color: yellow;  
  background-color: transparent;  
  text-decoration: underline;}  
</style>
```

