- You can add this a reset to pretty much every project 
```css
*, *::before, *::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  /** things that are universal to THIS app, but not necessarily others like font, font-size */
  font-family: Ariel;
  font-size: 62.5%;
  color: black;
}
```

- Border box makes it so the border you added doesn't add any size to your elements.

Browsers can apply default margin and padding values to specific elements. To make sure your piano looks correct, you need to reset the box model.

Now that you have reset the `html` box model, you need to pass that on to the elements within as well. To do this, you can set the `box-sizing` property to `inherit`, which will tell the targeted elements to use the same value as the parent element.

You will also need to target the pseudo-elements, which are special keywords that follow a selector. The two pseudo-elements you will be using are the `::before` and `::after` pseudo-elements.

The `::before` selector creates a pseudo-element which is the first child of the selected element, while the `::after` selector creates a pseudo-element which is the last child of the selected element. These pseudo-elements are often used to create cosmetic content, which you will see later in this project.

