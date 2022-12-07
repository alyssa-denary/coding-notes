- Two types of animations:
	- Transition property: and then just changes the effects you want. Generally easier
	- Keyframes-at rule and animation property: More advanced

## Transition


## Keyframes
```css
.selector {
	width: 35%;
	height: 98%;
	animation-name: moveInLeft;
	animation-duration: 1s;
	animation-iteration-count: 3;
	animation-delay: 3s;
	animation-timing-function: ease-in; /* Look at MDN for more examples */
}

@keyframes moveInLeft {
	0% {
		opacity: 0;
		transform: translate(-100px);
	}

	80% {
		transform: translate(10px);
	}

	100% {
		opacity: 100%
		transform: translate(0);
	}
}
```

- Best to only animate two properties, as these are optimized for the browser:
		- Opacity
		- Transform (can do a whole lot with transform)

### Shaking
- Oftentimes some shaking happens with animations
- We don’t know why this happens
- To fix: 
	- On parent element, set backface-visibility to hidden
```css
.parent-selector {
	 backface-visibility: hidden;
}

.child-animated-selector {
	width: 35%;
	height: 98%;
	animation-name: moveInLeft;
	animation-duration: 1s;
	animation-timing-function: ease-in; /* Look at MDN for more examples */
}

@keyframes moveInLeft {
	0% {
		opacity: 0;
		transform: translate(-100px);
	}

	80% {
		transform: translate(10px);
	}

	100% {
		opacity: 100%
		transform: translate(0);
	}
}
```