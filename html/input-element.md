## Input Element
```html
<form action="where you want the data to go">
	<input type="search, text, password radio, checkbox" name="needed for processing data when it's sent to the form action location" placeholder="text that shows in the input field" required>
	<label><input type="radio">Radio Button</label> 
	<!-- Label used to wrap input type and associate it with the corresponding text -->
	<input id="loving" type="checkbox"> <label for="loving"> Loving </label>
	<!-- May also associate text with input by using a for attribute with the same value as the input's id -->
</form>
```

### Type attribute:
#### Text: User text to enter
#### Password: Hides text while typed with dots
#### Radio Buttons - single select
```html
<form action="http://www.catphotoapp.com">
	<fieldset>
		<legend>Is your cat an indoor or outdoor cat? </legend>
		<label><input id="indoor" type="radio" name="indoor-outdoor" value="indoor" checked> Indoor</label>
		<label><input id="outdoor" type="radio" name="indoor-outdoor" value="outdoor"> Outdoor</label>
	</fieldset>
</form>
```
	- Name attribute: For radio buttons, if you only want one option to be able to be selected at a time, these radio buttons must have the same name. Need name assigned to save data from text input as well.
	- Value attribute: Need to have value assigned to have useful data show up at the action page. Otherwise, just set to indoor-outdoor:on, & user selection is not clear/specified. Note that text input fields within forms have value assigned at submission of the form based on user typed input
	- Fieldset element: Used to group related inputs and labels together in a web form (note is a block level element)
	- Legend element: Acts as a caption for the content in the `fieldset` element. It gives users context about what they should enter into that part of the form.
	- Checked attribute: no assigned value, sets default selection
#### Checkboxes
```html
<fieldset>
	<legend>What's your cat's personality?</legend>
	<input id="loving" type="checkbox" name="personality" value="loving" checked> <label for="loving">Loving</label>
	<input id="lazy" type="checkbox" name="personality" value="lazy"> <label for="lazy">Lazy</label>
	<input id="energetic" type="checkbox" name="personality" value="energetic"> <label for="energetic"> Energetic</label>
</fieldset>
```
- Allows users to **multiselect** options
- Interactivity: best to use with [Change event listeners](../DOM-manipulation/event-listeners#Change)