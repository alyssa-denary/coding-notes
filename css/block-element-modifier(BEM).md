## Nesting
- always do with just one class selector
- with each just having one class selector, weren’t really seeing that much nesting
	- BUT: 
		- can nest with & operator
```scss
.header {
	// header css

	&_logo-box {
		// logo-box within header css
	}
}
```

