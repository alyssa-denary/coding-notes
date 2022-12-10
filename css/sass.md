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
