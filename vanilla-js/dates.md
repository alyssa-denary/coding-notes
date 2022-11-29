### Working with the current date:
- No args provided to Date()
```js
const now = new Date();
console.log(now.toString())
```

Prints:  `Tue Nov 29 2022 10:26:53 GMT-0500 (Eastern Standard Time)`

```js
console.log(`Year: ${now.getFullYear()}`); // Year: 2022

console.log(`Month: ${now.getMonth()}`); // Month: 10 **Note: zero indexed

console.log(`Day of month: ${now.getDate()}`); // Day of month: 29

console.log(`Hour: ${now.getHours()}`); // Hour: 10

console.log(`Minute: ${now.getMinutes()}`); // Minute: 41

console.log(`Seconds: ${now.getSeconds()}`); // Seconds: 20
```


### Working with specific date:
- Though possible, not common to pass a string for a date
  e.g.   `Date('January 21 2001 6:25:01')` 
- Instead, Unix Epoch used to numerically represent dates
  Unix Epoch - January 1 1970 00:00:00
  -All dates/times after this point represented using positive numbers
  -All dates/times before this point represented using negative numbers

To retrieve & store numerical representation of date/time:
```js
const timestamp = now.getTime();
```

To convert numerical representation back into date format:
```js
const myDate = new Date(timestamp);

console.log(myDate.getFullYear()); // 2022
```
- Pass in the numerical representation into the Date function.
- Now you can access helpful methods on the Date object to pull out day, month, year, hour, minutes, etc. 