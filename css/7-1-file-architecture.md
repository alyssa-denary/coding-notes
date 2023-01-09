## Partials
- Intended for multipage larger project (a bit overkill for a single page)
- partials/files typically start with underscore _

- & Example:
- `base` folder	
	-  `_base`
		- universal reset
			- margin
			- padding
			- box-sizing inherit
		- html
			- font-size: here and not in typography cause determines page proportions
			- media query mixins
		- body
			- box-sizing
			- everything typography related should go in typography file
	- `_utilities`
	- `_typography`
		- put into this folder all typography related properties: 
			- font-family
			- font-weight
			- color (font)
		- `body`
			- all typography related properties to apply to body selector
		- `_heading-primary` (from Natours project example) could argue this is a component, but gauge these decisions based on what seems most intuitive
	- `_animations`
		- keyframes
- `abstracts `folder
	- Only put code in this folder that is <u>not</u> going to output any CSS
	- `_variables`
		- color variable declarations
	- `_mixins`
	- `_functions`
- `components` folder
	- Put code that is a reusable building block that make up the website/app
		- should be completely independent, can be used anywhere in the page
		- held together by the layout of the page
	- `_button`
- `layout `folder
	- Put code that holds all of the components together
		- for each piece of the global layout of the entire project
		- should work everywhere and on all pages - for specific styles for specific page - use pages folder
	- `_header`
	- `_footer`
- `pages` folder
	- Put specific styles for specific pages in this folder
	- `_home`
- `themes` folder
	- Put code for cases with a web app with different themes in this folder
- `vendors `folder
	- Put code for 3rd party css, like:
		- CSS file for a bootstrap
		- Icon system
		- Animation framework

### Importing
- All partials must be imported into main file
	- Goal is for main file to have no code besides importing the partials
	- Import in same order as the files are listed
	- Note SCSS shorthand for importing: 
```scss
@import "base/base";  // equates to "base/_base.scss"
```

