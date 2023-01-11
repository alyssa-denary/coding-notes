## Nav list item hover effect
- Line shows then expands vertically

![[line-hover-animation.mov]]

### Steps:
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

