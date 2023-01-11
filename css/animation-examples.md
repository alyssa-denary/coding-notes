## Using Transition Property

### Nav list item - expanding line
- Line shows then expands vertically

![[line-hover-animation.mov]]

#### Steps:
1. add pseudoelement ::before to list item that will be the small line that will become visible and then grow to right side. Style like so:
```scss
.class-selector-for-li {
	position: relative;
	
	&:not(:last-child) {
		margin-bottom: 0.5rem; // To add margin bottom to all items except last one
	}
}

	&::before {
		content: ""; // Pseudo-el must have content to show on page at all
		position: absolute; // Remember parent element must be pos- relative
		top: 0; // Absolute pos & set to top & left of original list element
		left: 0;
		height: 100%; // To match height of list item
		width: 3px; // Width of line that first appears
		background-color: var(--color-primary); // Chosen background color
		transform: scaleY(0); // Just tranforms Y direction, 0 defines start
		transition: transform 1s; // 1s is slow animation for demonstration
	}
	
	&:hover::before {
		transform: scaleY(1);  // Where animation ends
	}
}
```

### Nav list item - expanding line + background color width expansion

![[line-and-width-animation.mov]]

#### Steps
1. Complete step above for expanding line
2. Add width post-state (:hover), and width to transition with delay matching duration of line-transform
3. Add transition effect - in this case cubic bezier was used on width
4. Add position and z-index to elements desired in foreground (i.e. “on top” of animation pseudoelement)
Final styling like so:

```scss
.class-selector-for-li {
	position: relative;
	
	&:not(:last-child) {
		margin-bottom: 0.5rem; // To add margin bottom to all items except last one
	}
}

	&::before {
		content: ""; // Pseudo-el must have content to show on page at all
		position: absolute; // Remember parent element must be pos- relative
		top: 0; // Absolute pos & set to top & left of original list element
		left: 0;
		height: 100%; // To match height of list item
		width: 3px; // Width of line that first appears
		background-color: var(--color-primary); // Chosen background color
		transform: scaleY(0); // Just tranforms Y direction, 0 defines start
		transition: transform .2s, width .4s cubic-bezier(1,0,0,1) .2s; 
	}
	
	&:hover::before {
		transform: scaleY(1);  // Where animation ends
		width: 100%; 
	}
}

.selector-for-text-and-foreground-elements {
	position: relative; // To make icon & words show on top of ::before pseudo-el
	z-index: 10; // z-index only works when position is specified
}
```

