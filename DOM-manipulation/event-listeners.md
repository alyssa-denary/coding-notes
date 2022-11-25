## Submit
```html
<form id="note-form">
	<input type="text" placeholder="Write note here" required />
	<button>Create note</button>
</form>
```
- Ideal event listener for when a [[form-element]] is submitted

## Click 


## Change
	- In reference to an input html element, a "change" event listener updates changes to the input element text whenever a user clicks away/removes focus from the input field
```html
<label>
	<input id="hide-all" type="checkbox"/> Hide all
	</label>
```

```js
document
.querySelector("#note-input")
.addEventListener("change", function (e) {
	console.log(e.target.value);
});
```
- Prints to the console whenever user clicks away
- Good to use for [Checkboxes](../html/input-element#Checkboxes) and [Dropdowns](../html/select-element#Dropdowns)

![[Screen Shot 2022-11-15 at 10.38.51 AM.png]]

## Input
	- By comparison, in reference to an input html element, an "input" *event* updates changes to the input element text whenever a character change occurs (i.e. in real time)
```html
<!-- Same as above -->
```

```js
document
.querySelector("#note-input")
.addEventListener("input", function (e) {
	console.log(e.target.value);
});
```
	- Note only difference in js is event type. 
	- Prints to console whenever any char change occurs/ each state the input was in
	- Much more useful for 99% of cases

![[Screen Shot 2022-11-15 at 10.37.18 AM.png]]

## Storage
	- Special event listener for global variable changes in storage
	- e with storage includes a few specific properties: 
		- key
		- newValue
		- oldValue
```js
window.addEventListener("storage", (e) => {
	// Checks that the key matches intended storage listener
	if (e.key === "notes") {   // Or other targeted key name
		notes = JSON.parse(e.newValue);  // save parsed info into variable
		note = notes.find((el) => el.id === noteID);  // finds specific note

		// Sends users back to homepage if note does not exist or was deleted
		if (note === undefined) { 
			location.assign("index.html");
		}

		// Updates title and body values to newest saved info
		noteTitle.value = note.title;
		noteBody.value = note.body;
	}
});
```


