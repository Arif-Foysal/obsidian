#css 

CSS selectors allow us to choose specific elements and apply styles to them.

### **Types of CSS Selectors**
1. [[CSS Selectors#Universal Selector|Universal Selector]]
2. [[CSS Selectors#Element Selector|Element Selector]]
3. [[CSS Selectors#ID Selector|ID Selector]]
4. [[CSS Selectors#Class Selector|Class Selector]]
5. [[CSS Selectors#Group Selector|Group Selector]]

#### **Universal Selector**
Targets all the HTML elements on the page.
```css
* {
    property : value;
}
```
#### **Element Selector**
The element selector selects the target element based on the specific type.
```css
p {
    property : value;
}
```
#### **ID Selector**
The ID selector targets the elements based on the specific ID. It is written with the hash **“**#**”** character followed by the ID name in the style sheet.
```css
#ID {
    property : value;
}
```
#### **Class Selector**
```css
.class {
    property : value;
}
```
#### **Group Selector**
```css
div, p, a {
    property : value;
}
```

