- The `::before` element creates a **pseudo-element** which is the first child of the selected element, while the `::after` selector creates a pseudo-element which is the last child of the selected element. 
	- To create the black keys, add a new `.key.black--key::after` selector. This will target the elements with the class `key black--key`, and select the pseudo-element after these elements in the HTML. #refactor 
	- In the new selector, set the `background-color` to `#1d1e22`. Also set the `content` property to `""`. This will make the pseudo-elements empty.
	- The `content` property is used to set or override the content of the element. By default, the pseudo-elements created by the `::before` and `::after` pseudo-selectors are empty, and the elements will not be rendered to the page. Setting the `content` property to an empty string `""` will ensure the element is rendered to the page while still being empty.

- The :before pseudo-selector #add 
```css
p::before {
	content: "Question #";
}
```

- The `::after` element creates like a virtual element right after the actual HTML element that we are selecting (the element selected just to the left of `::after`).
	- You can then style this element to create additional effects.
	- In order for the after element to show on the page, must have:
		- content
		- display
		- basically treated like a child of the html element selected
	- Note that if within a flex container, will be affected by flex properties on that container (justify-content, etc.)

