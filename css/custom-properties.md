### CSS custom properties:
- Custom properties are a way to set your own variables.
- Typically and often used for colors. 
- Built into CSS: Custom properties cascade and inherit (making them better than sass variables), they can be manipulated in javascript, edited with dev tools, easier to use in code function. 
- Add for all colors used within a project. Generally not recommended to use standard/built in colors (even black/white) as these are arbitrarily chosen.
- Companies tend to have own set of colors chosen/approved that are then stored in custom properties

```css
// Declaring custom color properties:
:root {
	--faintGrey: rgb(248, 248, 248);
	--liteGrey: rgb(241, 241, 239);
	--lineGrey: rgb(230, 227, 227);
	--medGrey: #67696b;
	--darkGrey: rgb(112, 111, 111);
	--darkestGrey: rgb(71, 71, 71);
	--signInBlue: #1a73e8;
	--washedBlue: #3b70b5;
}

// Using custom properties:
footer {
	position: absolute;
	bottom: 0;
	width: 100%;
	display: flex;
	background-color: var(--liteGrey);
	justify-content: space-between;
	align-items: center;
	padding: 15px 0px;
}
```
