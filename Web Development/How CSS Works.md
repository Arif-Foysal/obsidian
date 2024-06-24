#css 

1. The user types the URL and clicks enter.
2. The browser makes a fetch request to the server.
3. HTML is fetched from the server.
4. HTML is converted into a DOM. In the DOM, each tag is considered a **node**.
5. The browser fetches all the related files and assets that are linked to that HTML, such as external CSS, fonts, images, etc.
6. The browser then parses the CSS and groups it based on the selectors, which can be tags.
7. Each CSS is attached to its respective node. In this phase, CSS gets attached to its respective node. This is called a **render tree**.
8. The render tree is the well-structured, well-arranged **DOM** node that will appear on the screen.
9. The well-structured, custom-designed website is presented on the screen. This is called **painting**.

**ref:** https://www.codewithharry.com/tutorial/how-css-works/,
https://developer.mozilla.org/en-US/docs/Web/CSS

