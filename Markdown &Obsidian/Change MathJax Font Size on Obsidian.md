To Change the MathJax font size in Obsidian, you can follow these steps:

1. Open your Obsidian vault.
    
2. Locate the `.obsidian` folder within your vault. This folder contains the configuration files for Obsidian.
    
3. If you don't already have a `snippets` folder inside the `.obsidian` folder, create one.
    
4. Inside the `snippets` folder, create a new file with a `.css` extension. You can name it something like `mathjax-font-size.css`.
    
5. Open the `mathjax-font-size.css` file in a text editor.
    
6. Add the following CSS code to increase the font size:
    
```css
	.math {
  font-size: 18px; /* Adjust the value to your desired font size */
}
```
	
 In this example, the font size is set to `18px`. You can modify this value to your preferred font
2. Save the file.

4. Switch back to Obsidian and reload the CSS snippets by going to `Settings -> Appearance -> CSS Snippets` and disabling and re-enabling the CSS Snippets option.
    
4. Now, the MathJax font size should be increased in your Obsidian notes.
    

Note: If you're already using a custom CSS file or theme, you can add the MathJax font size code to that file instead of creating a separate snippet.

Remember to adjust the font size value to suit your needs. You can experiment with different values until you find the font size that works best for you.