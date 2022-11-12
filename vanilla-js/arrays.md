Array.prototype.sort
Sort takes an optional callback function to determine sorting order.
This is particularly useful if sorting an array of objects
```js
const sortToDos = (array) => {

	array.sort((a, b) => {
		if (a.completed === true && b.completed === false) {
			return 1;
		} else if (
			b.completed === true && a.completed === false) {
			return -1;
		} else {
			return 0;
		}
	});
	return array;
};
```

