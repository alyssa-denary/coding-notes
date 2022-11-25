## Bubble Sort
- Iterates through - checking which value is bigger. If first value bigger than second value, swaps them. So, by end of first iteration, largest value “bubbles” to the end of the array. Iteration continues until all values sorted.
- Time complexity is O(n**2) Quadratic time b/c in worst case, each element needs to be compared n times. 
- Implementation with opimizations: 
	- iterating 1 fewer elements on each pass (b/c last item on each pass is now sorted)
	- if on last pass no swaps were made, array is sorted and loop is exited
```js
function bubbleSort (array){
  let noSwaps;
  for (let i = array.length - 1; i >= 0; i--){
    noSwaps = true;
    for (let j = 0; j < i; j++){
      if (array[j] > array[j+1]) {
        let temp = array[j];
        array[j] = array[j+1];
        array[j+1] = temp;
        noSwaps = false;
      }
    }
    if (noSwaps) break;
  }
  return array;
}

console.log(bubbleSort([3, 1, 2, 9, 4, 23, 7]));
```

## Selection Sort
- Iterates through whole array looking for the minimum. After iteration, swaps placement of minimum value with the first element. Continues until passes completed for each element.
- Time complexity is O(n**2) Quadratic time
- Implementation with optimization:
	- not swapping if minInd is already the same as i (array is in order)
```js
function selectionSort (array){
  for (let i = 0; i < array.length; i++){
    let minInd = i;
    for (let j = i + 1; j < array.length; j++){
      if (array[j] < array[minInd]) {
        minInd = j;
      }
    }
    if (minInd !== i){
      ([array[i], array[minInd]] = [array[minInd], array[i]]); // ES6 for swapping vals
    }
  }
  return array;
}

console.log(selectionSort([3, 1, 2, 9, 4, 23, 7]));
```