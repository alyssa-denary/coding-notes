## Label Element: 
- Used to wrap input type and associate it with corresponding text
  ```html
  <form action="where you want the data to go">
	<input type="search, text, password radio, checkbox" name="needed for processing data when it's sent to the form action location" placeholder="text that shows in the input field" required>
	<label><input type="radio">Radio Button</label> 
	<!-- Label used to wrap input type and associate it with the corresponding text -->
	<input id="loving" type="checkbox"> <label for="loving"> Loving </label>
	<!-- May also associate text with input by using a for attribute with the same value as the input's id -->
</form>
```
- can accomplish in 2 ways: 
	- wrapping around input
	- using for attribute and giving it the same string as an input’s id (useful if positioning label further away from the input(?)) #questions 