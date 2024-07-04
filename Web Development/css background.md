#css 

The CSS background property helps set the background style, property, and effects of the element.
There are various background properties, such as:
- `background-color`
- `background-image`
- `background-repeat`
- `background-attachment`
- `background-position`
- `background` (shorthand property)

## Shorthands

All the background properties would look something like this in a single line.
### Syntax
```css
selector{
    background: [background-color] [background-attachment] [background-image] [background-repeat] [background-position];
}
```
#### Example:
```css
div{
    background: purple fixed url("./harrybhai.png") no-repeat right top;
}
```



## Background color

The background color property sets the background colour of HTML tags such as div, section, p, etc.

### **Syntax:**

```css
selector{
      background-color: color;
}
```

## Background Image

The Background Image property sets an image as a background by providing the image URL within the **url()** function.
### Syntax:

```css
selector{
        background-image: url('image-url');
}
```
#### Example:

```css
<style>
        div{
            background-image: url('harrybhai.png');
        }
</style>
```

The image is **repeated** many times because CSS repeats the image by default on both the x and y axes, to avoid leaving empty spaces due to the image dimensions. To solve this issue, use the background property.

## Background repeat

Background repeat helps to control how the image will repeat.

### Syntax

```
selector{
   background-repeat: repeat-x || repeat-y || repeat[repeat both directions, this is by default] || no-repeat;
}
```

background-repeat can be set to repeat, no-repeat, repeat-x (horizontal), or repeat-y (vertical).

## Background Size

The Background Size property sets custom sizes for the background image.

```css
selector{
    background-size: propery-value;
}
```

Property-value can be any of the following:
### cover: 

The image fits the width of the background area according to the dimensions; the background area will be completely covered by the image while maintaining its aspect ratio.

#### Syntax

```css
div{
     background-image: url("./harrybhai.png");
     background-size: cover;
}
```

### contain: 

Scales the image to fit the height within the background area while maintaining its aspect ratio.
#### Syntax:

```css
div{
    background-image: url("./harrybhai.png");
    background-size: contain;
}
```

### auto
The image will be displayed in its original size. This is the default.

```css
div{
    background-image: url("./harrybhai.png");
    background-size: auto;
}
```

### Distinct width and height
We can manually set the width and height of the background image.
#### Syntax:

```css
div{
    background-image: url("./harrybhai.png");
    background-size: 100% 100%;
}
```

**Note:** The width and height are used in percentage(%);

## Distinct width and height

We can manually set the width and height of the background image.

### Syntax:

```css
div{
    background-image: url("./harrybhai.png");
    background-size: 100% 100%;
}
```

Copy

**Note:** The width and height are used in percentage(%);
## Background Position

This property sets the starting position of the background image within the container (parent div).

By default, the position is **top left**.
### Syntax:
```css
selector{
     background-position: property-value;
}
```

Property value can be **top, bottom, left, right, or center.** We use combinations of positions such as top left, top right, bottom left, bottom right, center, etc.
#### Example:

```css
div{
     background-image: url("./harrybhai.png");
     background-repeat: no-repeat;
     background-position: top right;
}
```

Copy
## Background Attachment
The background-attachment property determines whether the background image scrolls with the content.
#### Syntax:

```css
div{
    background-attachment: fixed || scroll;
}
```

Use fixed for a fixed background, or scroll for a scrolling background.

