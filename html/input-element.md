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

### Type attributes:
#### Password: Hides text while typed with dots
```html

```
#### Text
- Text input allows users to enter text 
- & Interactivity: Two main ways of interacting with text inputs:
1. **Form submissions:** When nested in a form, would target the form ID and look for a [change](../DOM-manipulation/event-listeners#Change) event listener.
	  <form id="cat-name" action="http://www.catphotoapp.com">
	<label>Cat's Name:<input type="text" name="catName" placeholder="Your cat's name" required> </label>
	<button>Submit</button>
</form>
```html
<form id="cat-name" action="http://www.catphotoapp.com">
	<label>Cat's Name:<input type="text" name="catName" placeholder="Your cat's name" required> </label>
	<button>Submit</button>
</form>
```
2. **Updates in real time:** Examples of this is a search bar, and results show in real time as the user enters text. For this, would need to target the input ID, and use a [input](../DOM-manipulation/event-listeners#Input) event listener. 
   <label>Search: <input id="cat-search" type="text" placeholder="Type cat to search"> </label>
   ```html
<label>Search: <input id="cat-search" type="text" placeholder="Type cat to search"> </label>
```

#### Radio
<form action="http://www.catphotoapp.com">
	<fieldset>
		<legend>Is your cat an indoor or outdoor cat? </legend>
		<label><input id="indoor" type="radio" name="indoor-outdoor" value="indoor" checked> Indoor</label>
		<label><input id="outdoor" type="radio" name="indoor-outdoor" value="outdoor"> Outdoor</label>
	</fieldset>
</form>
```html
<form id="where-live" action="http://www.catphotoapp.com">
	<fieldset>
		<legend>Is your cat an indoor or outdoor cat? </legend>
		<label><input id="indoor" type="radio" name="indoor-outdoor" value="indoor" checked> Indoor</label>
		<label><input id="outdoor" type="radio" name="indoor-outdoor" value="outdoor"> Outdoor</label>
	</fieldset>
</form>
```
- Radio Buttons allow users to **single select** an option
  
#### Checkboxes
<form id="cat-personality">
	<fieldset>
		<legend>What's your cat's personality?</legend>
		<input id="loving" type="checkbox" name="personality" value="loving" checked> <label for="loving">Loving</label>
		<input id="lazy" type="checkbox" name="personality" value="lazy"> <label for="lazy">Lazy</label>
		<input id="energetic" type="checkbox" name="personality" value="energetic"> <label for="energetic"> Energetic</label>
	</fieldset>
</form>
```html
<form id="cat-personality" action="http://www.catphotoapp.com">
	<fieldset>
		<legend>What's your cat's personality?</legend>
		<input id="loving" type="checkbox" name="personality" value="loving" checked> <label for="loving">Loving</label>
		<input id="lazy" type="checkbox" name="personality" value="lazy"> <label for="lazy">Lazy</label>
		<input id="energetic" type="checkbox" name="personality" value="energetic"> <label for="energetic"> Energetic</label>
	</fieldset>
</form>
```
- Checkboxes allow users to **multiselect** options.
- Note other aspects shown in HTML above:
	- [Fieldset](fieldset-element) with [legend](legend-element)
	- Labels referencing input’s id (note this is an example of why an input would maintain an id even though it is nested within a form
- & Interactivity: best to use with [Change event listeners](../DOM-manipulation/event-listeners#Change), and note that for checkboxes, you target `e.target.checked` (shown below)
```js
document.querySelector('#delivery').addEventListener('change', function (e) { console.log(e.target.checked) });
```

### Name Attributes:
 - Name attribute: For [radio](#Radio) #tofix, if you only want one option to be able to be selected at a time, these radio buttons must have the same name. Need name assigned to save data from text input as well.

### Value Attributes:
- Value attribute: Need to have value assigned to have useful data show up at the action page. Otherwise, just set to indoor-outdoor:on, & user selection is not clear/specified. Note that text input fields within forms have value assigned at submission of the form based on user typed input
- For [select](select-element) elements and options that are used as dropdown selections: value of the select element depends on the option that was clicked. If the option has a value attribute set, than that attribute’s value will be used. If the option does not have a value, than the option text will be used. 

### Checked Attribute
 Checked attribute: no assigned value, sets default selection