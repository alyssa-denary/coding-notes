## Dropdowns
```html
<select id="filter-by">
	<option value="byEdited">Sort by last edited</option>
	<option value="byRecent">Sort by recently created</option>
	<option value="byAlphabetical">Sort alphabetically</option>
</select>
```
- [[event-listeners#Change]]  is the best event listener to use for dropdowns. Example JS is shown below:
```js
document.querySelector('#filter-by').addEventListener('change', function (e) {
	console.log(e.target.value)
});
```
  - Upon user selecting a new option, the corresponding option’s value would print to console (“byEdited”, “byRecent”,  or “byAlphabetical”).