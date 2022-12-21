## Sass - most popular
- a preprocesser for CSS (other preprocessers like less and stylus exist)
- adds power and elegance to CSS
- needs to be processed first, then compiled into CSS to work in the browser


### Implementing Sass with NPM
- For using sass
	- create a new folder to hold sass files
		- remember there are two syntaxes, scss and sass
			- save file with extension `.scss` 
- How to use the node-sass package you installed?
	- use by writing an npm <u>script</u> in <u>package.json file</u>
	- See sample script below, basically writing the terminal commands to execute, but wouldn’t work if you just ran this command in terminal.
```json
{
	"name": "natours",
	"version": "1.0.0",
	"description": "Landing page for natours",
	"main": "index.js",
	"scripts": {
		"compile:sass": "node-sass sass/main.scss starter/css/style.css"
	},
	"repository": {
		"type": "git",
		"url": "git+https://github.com/alyssa-denary/advanced-css-course.git#main"
	},
	"keywords": [
		"nature",
		"tours"
	],
	"author": "Alyssa",
	"license": "ISC",
	"bugs": {
		"url": "https://github.com/alyssa-denary/advanced-css-course/issues"
	},
	"homepage": "https://github.com/alyssa-denary/advanced-css-course/tree/main#readme",
	"devDependencies": {
		"node-sass": "^8.0.0"
	}
}
```
- To execute this compilation, will then need to execute this command while <u> in the same folder as your package.json file</u> 
	- `npm run *script:name*`  so for example above `npm run compile:sass`

### Main features of Sass 
- **Variables:** for reusable values such as colors, font-sizes, spacing, etc. 
- **Nesting:** to nest selectors inside of one another, allowing us to write less code.
- **Operators:** for mathematical operations right inside of CSS
- **Partials and Imports:** to write CSS in different files and import them all into one single file
- **Mixins:** to write reusable pieces of CSS code
- **Functions:** similar to mixins, with the difference that they produce a value that can than be used
- **Extends:** to make different selectors inherit declarations that are common to all of them
- **Control Directives:** for writing complex code using conditionals and loops 

### Syntax
- Sass - #add 
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
##### Mixins and media queries
- With sass, can also write media query within selector:
```scss
.selector  {
	font-size: 62.5%;
	@media (max-width: 600px) {
		font-size: 50%;
	}
}
```
- BUT, would have to write a query for each selector (whether within each selector or one big query)
	- Instead, better to write a mixin that will do this work for us
###### Content Directive
- Allows us to pass a block of code into a mixin
- Example:
```scss
/* Example abstracts/_mixins.scss file */

/* 
Media Query Manager:
0 - 600px: Phone
600 - 900px: Tablet portrait
900 - 1200px: Tablet landscape
[1200 - 1800]: Normal styles apply
1800 + :  Big desktop
*/

@mixin respond-phone {
	@media (max-width: 600px) { @content }
}

```
- With this content directive, you then need to have your original file that will pass content to this directive:
```scss
/* Example base/_base.scss file */
*,
*::before,
*::after {
	margin: 0;
	padding: 0;
	box-sizing: inherit;
}

html {
	font-size: 62.5%;

	@include respond-phone {  // New way: Phone query
		font-size: 50%;
	}

	@media (max-width: 900px) {  // Old way: Tablet query
		font-size: 50%;
	}
}

body {
	box-sizing: border-box;
}
```
- But still, with this way, you have multiple different mixins for each breakpoint. We want one large mixin with all the breakpoints
###### If directive
- Note refactor from media queries using pixels to those using ems
	- ems must be used instead of rems because those in media query are not affected by the root font-size setting. Instead, they respond to the browser default setting, so we use ems. 
	- Since 16px is typically the default browser font-size, this was used to calculate ems
		- $breakpoint - phone: 600/16 = 37.5 em
		- $breakpoint - tab-port 900/16= 56.25 em
		- $breakpoint- tab-land 1200/16= 75 em
		- $breakpoint- big desktop 1800/16= 112.5 em
```scss
/* Example abstracts/_mixins.scss file */

/* 
Media Query Manager:
0 - 600px: Phone
600 - 900px: Tablet portrait
900 - 1200px: Tablet landscape
[1200 - 1800]: Normal styles apply
1800 + :  Big desktop
*/

/* 
$breakpoint argument choices:
- phone
- tab-port
- tab-land
- big-desktop
*/

@mixin respond($breakpoint) {
	@if $breakpoint == phone { 
		@media (max-width: 37.5em) { @content };  //600px
	}
	@if $breakpoint == tab-port { 
		@media (max-width: 56.25em) { @content }; //900px
	}
	@if $breakpoint == tab-land { 
		@media (max-width: 75em) { @content }; //1200px
	}
	@if $breakpoint == big-desktop { 
		@media (min-width: 112.5em) { @content }; //1800px
	}
}
```

```scss
/* Example base/_base.scss file */

*,
*::before,
*::after {
	margin: 0;
	padding: 0;
	box-sizing: inherit;
}

html {
	font-size: 62.5%;

	@include respond(phone) { 
		font-size: 50%;
	}

	@include respond(tab-port) { 
		font-size: 60%;
	}

	@include respond(tab-land) {  
		font-size: 70%;
	}

	@include respond(big-desktop) { 
		font-size: 80%;
	}
}

body {
	box-sizing: border-box;
}
```

###### Modifying responsiveness
- Can modify font-size now within each which will now change all other values since we set those based on rem. 
```scss
/* Example base/_base.scss file */

*,
*::before,
*::after {
	margin: 0;
	padding: 0;
	box-sizing: inherit;
}

html {
	font-size: 62.5%;

	@include respond(phone) { 
		font-size: 50%;
	}

	@include respond(tab-port) { 
		font-size: 50%;  // 1 rem = 8 px, 8/16 = 50%
	}

	@include respond(tab-land) {  
		font-size: 56.25%%; // 1 rem = 9px, 9/16 = 56%
	}

	@include respond(big-desktop) { 
		font-size: 75%;  // 1 rem = 12px, 12/16 = 75%
	}
}

body {
	box-sizing: border-box;
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
