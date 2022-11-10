## Frequency Counter


## Multiple Pointers



## Sliding Window
- Two loops:
	- First loop sets a 'standard'
	- Second loop moves like a sliding window, "Adding" in some way the next element while "removing" the previous element.
```js
 /** Given an array of integers and a number, write a function called **maxSubarraySum**, which finds the maximum sum of a subarray with the length of the number passed to the function.

Note that a subarray must consist of _consecutive_ elements from the original array. In the first example below, [100, 200, 300] is a subarray of the original array, but [100, 300] is not. */
function maxSubarraySum(array, num){
    if (array.length < num) return null;
    // have variable for sum
    let maxSum = 0;
    // first loop grabs first num numbers & updates sum
    for (let i = 0; i < num; i++){
      maxSum += array[i];
    }
  	let currentSum = maxSum;
    // second loop starts at num index, goes through and 
    for (let j = num; j < array.length; j++){
      	currentSum += array[j] - array[j - num];
        // adds next element, subtracts first element and checks if larger than sum 
        if (currentSum > maxSum){
            // updates sum if so 
            maxSum = currentSum;
        }
    }
    return maxSum; 
}

console.log(maxSubarraySum([100,200,300,400], 2)); // 700
console.log(maxSubarraySum([1,4,2,10,23,3,1,0,20], 4));  // 39 
console.log(maxSubarraySum([-3,4,0,-2,6,-1], 2)); // 5
console.log(maxSubarraySum([3,-2,7,-4,1,-1,4,-2,1],2)); // 5
console.log(maxSubarraySum([2,3], 3)); // null
```