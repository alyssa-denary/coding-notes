## BEM naming
block element modifier

always do with just one class selector
- with each just having one class selector, weren’t really seeing that much nesting
	- BUT: 
		- can nest with &
```scss
.header {
	// header css

	&_logo-box {
		// logo-box within header css
	}
}
```

