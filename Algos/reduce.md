## Array.prototype.reduce()
- when using reduce, be aware that this is the MOST flexible and powerful array method, but also the most difficult array method to understand by a large margin
- The first thing to understand is what the other common array methods do:
  1.  forEach() - doesn’t return anything, but you can do stuff.  
    if you ever `return arr.forEach(() => { // code })`, that will ALWAYS be undefined.
    2.  map() - returns an array. You can control some logic, but the length of the returned array will always be the same length as the original array. return [1,2,3].map(() => { return stuff }) will always return another array that has a length of 3!
    3.  filter() - returns an array. You can control logic, and the length will vary
    4.  every() / some() - returns a boolean
    5.  reduce() - can return ANYTHING. number, string, boolean, array, object, function!

```
const arr = ['a', 'b', 'c'];

// as a reminder, the reduce method takes in 2 args. The first is a function which automatically has 3 parameters (accumulator, current, and index) that you can use inside the function body. The second is a default value of ANY type

arr.reduce((acc, curr, index) => {
  // index is the index of this item. for this example, it will be 0 or 1 or 2
  // curr is the array item on this index. for this example, it will be 'a' or 'b' or 'c'
  // the acc for ONLY index 0 is the optionalStartingVal, which can be ANY DATA TYPE!
    // starting index 1, the acc is whatever that's returned BELOW this
  return <this becomes the acc of the next index!>
}, <optionalStartingVal>)
```

## Using to refactor a counter
- if you ever find yourself using this shape (which isn’t bad at all)
```
let counter = 0;
arr.forEach(i => {
  // change counter based on i
})
return counter;
```
- You can almost always refactor it to something better with reduce shape
```
return reduce((acc, curr) => {
return // change acc based on curr
```
since that second arg, 0 is exactly used for what we’re calling counter in the first example  
}, 0)
- This is code you’ll find in production in real companies
- see `count_matches` series of algos

## Practice Problems
```
/ task 1 - walk through this code line by line and explain what’s happening with each reduce iterationfunction reduce1(arr) {  
  return arr.reduce((acc, curr) => {  
    return acc;  
  }, []);  
}reduce1([1, 10, 100]);// the second arg, [] is the initial acc  
// the empty array is being passed to every iteration  
// final value is []
```

```
// task 2 - walk through this code// reduce2  
function reduce2(arr) {  
  return arr.reduce((acc, curr) => {  
    return acc;  
  }, true);  
}reduce2([1, 10, 100]);// the starting value now is a boolean, true  
// each iteration is passing true to the next  
// final value is true
```

```
// task 3 - now think about how the output would change if the 2nd arg was an empty array or an empty object
// note how the reduce method can return ANY type!
```

```
//refactor this function so it doesn’t use a counter variable or a for loop or a while loop  
hint: you can do this as one statementfunction countEvens(arr) {  
  let counter = 0;  
  for (const num of arr) {  
    if (num % 2 === 0) counter++;  
  }  
  return counter  
}
```
