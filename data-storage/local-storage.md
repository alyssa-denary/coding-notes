- all of the methods we use for local storage live on localStorage variable

## CRUD: Create, Read, Update, Delete
### Create
```js
localStorage.setItem("location", "Philadelphia");
```
- First arg is key, second arg is value
### Read
```js
console.log(localStorage.getItem("location"));
```
- arg is key, return value is the value from that key
#### In browser
- Can look for what is stored in local storage in browser under developer tools “storage” tab
### Update
```js

```
- also just uses setItem
- just use setItem with a different value
### Delete
```js
localStorage.removeItem("location");
```
- Takes one arg, key. Removes that key/value pair
```js
localStorage.clear();
```
- Remove all data in local storage, all keys.

## JSON
### Storing Local Data
- localStorage at it’s source only supports storing strings
- Thus, need to store array data as a string to be useful.
	- Use JSON stringify
```js
const user = {
	name: 'Andrew',
	age: 27
}

const userJSON = JSON.stringify(user);
console.log(userJSON);
```
- Must always use double quotes with JSON
	- But never going to be directly writing JSON, so it’s okay to use single quotes in your object
### Using Local Data
- To retrieve stringified data from localStorage:
	- use JSON parse

```js
const userJSON = localStorage.getItem("user");
const user = JSON.parse(userJSON);
console.log(`${user.name} is ${user.age}`);
```
