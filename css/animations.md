- Two types of animations:
	- Transition property: and then just changes the effects you want. Generally easier
	- Keyframes-at rule and animation property: More advanced

## Transition
- Add transition property to initial state
	- May specify which properties to enable transformation/animation for, or just put all
	- Specify time
- Add transform and/or other properties to modify on animation states
```css
.selector:initial-state {
	transition: all 0.2s;
}

.selector:state-to-animate {
	transform: translateY(-3px);
	box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.selector:state-to-animate {
	transform: translateY(-1px);
	box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
```

- Example of making button hover effect, then “pressing down” effect when button clicked
```css
.btn:link,
.btn:visited {
	transition: all 0.2s;
}

.btn:hover {
	transform: translateY(-3px);
	box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2); /* Note box-shadow here vs active */
}

.btn:active {
	transform: translateY(-1px);
	box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2); /* Box-shadow becomes less upon clicking that adds to "pressing down" effect */
}
```

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
		transform: translateX(-100px);
	}

	80% {
		transform: translateX(10px);
	}

	100% {
		opacity: 100%
		transform: translate(0);
	}
}
```

- Best to only animate two properties, as these are optimized for the browser:
		- Opacity
		- [Transform](transform) (can do a whole lot with transform)

### animation shorthand
```css
.selector-all-options {
	animation: duration | easing-function | delay | iteration-count | direction | fill-mode | play-state | name;
}

.selector-using-all-options {
	animation: 3s ease-in 1s 2 reverse both paused slidein;
}

```

```css
.selector-some-options {
	animation: duration | easing-function | delay | name;
}

.selector-using-some-options {
	animation: 3s linear 1s slidein;
}
```
- Important that:
	- Order of time values are preserved: especially when some values are omitted, first element parsed as time will be duration, second will be delay, etc.
	- Animation name is given as last argument.

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

## Accessibility
- Use a [Reduced Motion Media Query](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) to create a complimentary experience for users who have expressed a preference for reduced animated experiences.