# MOVE ZEROES

### High level idea

The array can be traversed and if a zero is encountered, it is deleted from the array then inserted at the end of the array. The only caveat to this is to be mindful of if a zero is deleted and the array is being iterated over, care must be taken because if the loop continues after deleting an element, elements will be skipped and not be checked. To take care of this, if a zero is deleted, do not increment the loop to check the next element because a new element was just "moved down" into the index where the zero was previously. If the loop does not increment when a zero is deleted and inserted at the end, then once the zeroes are at the end of the array, the zeroes will constantly be deleted and inserted at the end, causing an infinite loop. To handle this, another variable can be used to keep track of how many times the total loop has been executed. Every element needs to be checked once, so this variable serves as a counter to check that every single variable is only touched one time. This prevents the infinite loop.

### Time and space complexity

Let `n` be the size of the input array:

- Time: `O(n)` <br>
- Space: `O(1)` <br>

As stated in the problem, no additional space should be used. Every element in the array needs to be checked, so the time complexity is linear with respect to the size of the array.
