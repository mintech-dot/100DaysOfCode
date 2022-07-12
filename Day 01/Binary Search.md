**Binary search** is a textbook algorithm based on the idea to compare the target value to the middle element of the array.

If the target value is equal to the middle element - we're done.
If the target value is smaller - continue to search on the left.
If the target value is larger - continue to search on the right.

![[binary-search.jpg]]

**Algorithm**

-   Initialise left and right pointers : `left = 0`, `right = n - 1`.
    
-   While `left <= right` :
    
    -   Compare middle element of the array `nums[pivot]` to the target value `target`.
        
        -   If the middle element _is_ the target `target = nums[pivot]` : return `pivot`.
            
        -   If the target is not yet found :
            
            -   If `target < nums[pivot]`, continue the search on the left `right = pivot - 1`.
                
            -   Else continue the search on the right `left = pivot + 1`.


Below is the implementation of Binary Search in JavaScript:

```js script


var search = function(nums, target) {

	let left = 0 ;
	let right = nums.length -1;

while (left <= right) {

		const middle = Math.floor( ((left + right) / 2) );
		const current = nums[middle];

		if (current == target) {

			return middle;

		} else if (current < target) {

		// ignore the left part from the array and the current index

			left = middle + 1 ;

		} else {

		// ignore the right part from the array and the current index

			right = middle - 1;

		}

	}

	// return -1 if middle did never equal the target

	return -1;

};

```
