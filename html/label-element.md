## Label Element: 
- Used to wrap input type and associate it with corresponding text
  ```html
  <form action="where you want the data to go">
	<input type="search, text, password radio, checkbox" name="needed for processing data when it's sent to the form action location" placeholder="text that shows in the input field" required>
	<label><input type="radio">Radio Button</label> 
	<!-- Label used to wrap input type and associate it with the corresponding text -->
	<input id="loving" name="loving" type="checkbox"> <label for="loving"> Loving </label>
	<!-- May also associate text with input by using a for attribute with the same value as the input's id -->
</form>
```
- can accomplish in 2 ways: 
	- wrapping around input
	- using for attribute and giving it the same string as an input’s id (useful if positioning label further away from the input(?)) #questions 
	- Although not required for `label` elements with a nested `input`, it is still best-practice to explicitly link a `label` with its corresponding `input`, `textarea`, or `select` element. 
	- & Also give the corresponding `input`, `textarea`, or `select` element’s a matching name attribute to the id and the label’s for attribute.

#refactor 
The `rem` unit stands for root `em`, and is relative to the font size of the `html` element.

As `label` elements are inline by default, they are all displayed side by side on the same line, making their text hard to read. To make them appear on separate lines, add `display: block` to the `label` element, and add a `margin` of `0.5rem 0`, to separate them from each other.

###### label & for
Following accessibility best practices, link the `input` elements and the `label` elements together using the `for` attribute.

Use `first-name`, `last-name`, `email`, and `new-password` as values for the respective `id` attributes.

##### type attribute
Specifying the `type` attribute of a form element is important for the browser to know what kind of data it should expect. If the `type` is not specified, the browser will default to `text`.

Give the first two `input` elements a `type` attribute of `text`, the third a `type` attribute of `email`, and the fourth a `type` attribute of `password`.

The `email` type only allows emails with a `@` and a `.` in the domain. The `password` type obscures the input, and warns if the site does not use HTTPS.