- other preprocessers like less and stylus exist

## Sass - most popular
- a preprocesser for CSS
- adds power and elegance to CSS
- needs to be processed first, then compiled into CSS to work in the browser

### Main features #refactor 
- variables
- nesting
- ![[preprocessers-1670596784992.jpeg]]

### Syntax
- Sass -
- SCSS - looks like CSS syntax, jonas’ preference

### Common use cases
#### Colors
- Can declare colors using $ defined variables and then use with $ label
```scss
* {
	margin: 0;
	padding: 0;
	}

$color-primary: #f9ed69; //yellow color

.nav {
	background-color: $color-primary;
}
```
- Functions for modifying colors:
	- darken()
	- lighten()
	- 
#### Nesting
- Instead of:
```css
.navigation {
	list-style: none;
}

.navigation li {
	display: inline-block;
	margin-left: 30px;
}

.navigation li:first-child {
	margin: 0;
}

.navigation li a:link {
	text-decoration: none;
	text-transform: uppercase;
}
```
- We can now write:
```scss
.navigation {
	list-style: none;

	li {
		display: inline-block;
		margin-left: 30px;

		&:first-child {
			margin: 0;
		}

		a:link {
			text-decoration: none;
			text-transform: uppercase;
		}
	}

}
```
- No limit to level of nesting.

#### Mixins
- To write reusable pieces of CSS code. Syntax very similar to functions
- Define mixins like so:
```scss
@mixin style-link-text($col) {
	text-decoration: none;
	text-transform: uppercase;
	color: $col;
}
```
- Use mixins like so (with color variable in example as well):
```scss
a:link {
	@include style-link-text($color-text-dark);
}

.btn-hot:link {
	@include style-link-text($color-text-light);
}
```

#### Functions
- To perform calculations to produce a value in CSS. 
- Declare a function: 
```scss
@function divide($a, $b) {
	@return $a / $b;
}
```
- Use a function:
```scss
nav {
	margin: divide(60, 2) * 1px;  // Calculated val 30px
}
```

#### Extends
- Instead of:
```scss
.btn-main:link,
.btn-hot:link {
	padding: 10px;
	display: inline-block;
	text-align: center;
	border-radius: 100px;
	width: $width-button;
	@include style-link-text ($color-link-light);
}

.btn-main {
	&:link {
		background-color: $color-secondary;
	}

	&:hover {
		background-color: darken($color-secondary, 15%)
	}
}

.btn-hot {
	&:link {
		background-color: $color-tertiary;
	}

	&:hover {
		background-color: darken($color-tertiary, 15%)
	}
}
```
- Can condense into:
	- Takes away repeating .btn-main:link
```scss
%btn-placeholder {
	padding: 10px;
	display: inline-block;
	text-align: center;
	border-radius: 100px;
	width: $width-button;
	@include style-link-text ($color-link-light);
}

.btn-main {
	&:link {
		@extends %btn-placeholder;
		background-color: $color-secondary;
	}

	&:hover {
		background-color: darken($color-secondary, 15%)
	}
}

.btn-hot {
	&:link {
		@extends %btn-placeholder;
		background-color: $color-tertiary;
	}

	&:hover {
		background-color: darken($color-tertiary, 15%)
	}
}
```
- Only use extends if rules that you are extending are inherently and thematically related
- #questions how often is this really used? only replaces the name and seems to make it unclear where that placeholder section is applied.
