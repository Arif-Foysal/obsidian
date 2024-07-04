#html 

HSL stands for hue, saturation, and lightness. This is another way to set colour properties.

Breaking each keyword:

### Hue(h)

- Hue represents the type of color. It is measured in degrees, and its value lies from 0 to 360.
- 0 degree represents black, 120 degree is for green, and 360 degree is for blue.

### Saturation (S):

- Saturation controls the intensity or purity of the color. It is measured in percentage, and its value lies between 0% and 100%.
- 0% saturation is no color (grayscale),  and 100% saturation is the most intense colour.

### Lightness (L):

- Lightness determines how light or dark the colour is. It is measured in percentage, and its value lies between 0% and 100%.
- 0% lightness represents pure black, 50% lightness represents normal colour, and 100% lightness is pure white.

#### Syntax:

```css
selector{
       color: hsl(hue, saturation, lightness);
}
```

Copy

#### Example:

```css
<head>
    <style>
        h1 {
            color: hsl(235, 100%, 50%);
        }
        p {
            color: hsl(0, 0%, 0%);
        }
    </style>
</head>

<body>
    <h1>CodeWithHarry</h1>
    <p>A Developer</p>
</body>

</html>
```

Copy

##### Output:

![cwh tutorial image](https://cwh-full-next-space.fra1.cdn.digitaloceanspaces.com/tutorial/css-colors/hsl.png)

https://www.w3schools.com/html/html_colors_hsl.asp


