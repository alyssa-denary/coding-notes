- A global variable provided by the browser
- Representation of browser window
- Contains lots of interesting info:
```js
window.innerHeight
window.innerWidth
window.console
window.document === document
window.localStorage
```

- To sync data across pages:
	- attach event listener to window to look for changes to localStorage
	- event listener type [storage] 
- Provides a way to attach listeners for global events