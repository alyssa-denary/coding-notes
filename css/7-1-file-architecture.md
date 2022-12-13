## Partials
- Intended for multipage larger project (a bit overkill for a single page)
- partials/files typically start with underscore _
- base folder	
	- - `_base`
	- `_utilities`
	- `_typography`
	- `_animations`
- abstracts folder
	- only going to put code in this folder that is <u>not</u> going to output any CSS
	- `_variables`
	- `_mixins`
	- `_functions`
- components folder
	- reusable building blocks that make up website/apps
	- should be completely independent, can be used anywhere in the page
	- held together by the layout of the page
	- 
- layout folder
	- holds all of the components together
	- for each piece of the global layout of the entire project
	- should work everywhere and on all pages - for specific styles for specific page - use pages folder
	- global header
	- global footer
	- etc.
- pages folder
	- specific styles for specific pages live in this folder
	- `_home`
- themes folder
	- for cases with a web app with different themes
- vendors folder
	- for 3rd party css, like:
		- CSS file for a bootstrap
		- Icon system
		- Animation framework

### Importing
- Need to import all partials into main file

