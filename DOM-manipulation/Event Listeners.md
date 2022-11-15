## Change
	- In reference to an input html element, a "change" event listener updates changes to the input element text whenever a user clicks away/removes focus from the input field
```html
<form>
	<input id="note-input" placeholder="Write note here" required />
	<button class="note-submit" type="submit">Create note</button>
</form>
```

```js
document
.querySelector("#note-input")
.addEventListener("change", function (e) {
	console.log(e.target.value);
});
```
	- Prints to the console whenever user clicks away
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




