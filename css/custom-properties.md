
### CSS custom properties:
- Add for every single color? including places that use standard black/white, etc. ? 
- Generally not recommended to use standard/built in colors, as these are arbitrarily chosen
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
