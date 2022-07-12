**Binary search** is a searching algorithm used in a sorted array by repeatedly dividing the search interval in half

- If the target value is equal to the middle element ==> we're done.
- If the target value is smaller ==> continue to search on the left.
- If the target value is larger ==> continue to search on the right.


The picture source : geeks for geeks 
<div align="center">
<img src="https://i.postimg.cc/3wCh8hh5/Binary-Search.png" >
</div>



**Algorithm**

-   Initialise left and right pointers : `left = 0`, `right =  nums.length - 1`.
    
-   While `left <= right` :
    
    -   Compare middle element of the array `nums[middle]` to the target value `target`.
        
        -   If the middle element _is_ the target `target = nums[middle]` : return `middle`.
            
        -   If the target is not yet found :
            
            -   If ` nums[middle] < target `, continue the search on the right `left = middle + 1`.
                
            -   Else continue the search on the left `right = middle - 1`.


Below is the implementation of Binary Search in JavaScript:

```js script
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */

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

	// return flase if middle did never equal the target

	return false;

};

```
