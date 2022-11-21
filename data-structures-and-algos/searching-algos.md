## Linear
- iterate over each of the items (forward or backward)
- performs at O(n) time

## Binary
- data must be sorted
- eliminates half of remaining elements (vs linear’s 1 at a time)
- checks middle and compares to val
	- if val less than/before val, eliminate the later half and just look at first half of values
	- then check middle of new data
		- etc. 