## Document Object Model Structure
- Document: HTML
- Object: Javascript Object that models the HTML document

#### Anytime we're using javascript to do something with our HTML most likely using the DOM

document is modeled using a javascript object, that object is called document.
	- provided to us by the browser

## Basic DOM manipulation:
1. Find the thing you're looking for by querying 
2. What you're going to do with the things you find

### Finding the things you're looking for
	- document.querySelector()
		- Argument(s): string containing one or more selectors to match.
		  Must be valid CSS selector string, else SyntaxError is thrown
		- Returns Element Object (representation of just matching element)
		- Matches & returns the first element found
	- document.querySelectorAll()
		- Argument(s): string containing one or more selectors to match.
		  	Must be valid CSS selector string, else SyntaxError is thrown
		- Returns an an array of all matching elements
		- To do something with each one, will need to iterate over the elements

### What you're going to do with what you find
- delete: remove() method
	- removes the selected element
- edit text: textContent property
	- Can access and/or reassign textContent to be alternative. Example of editing curse words to be ******
	