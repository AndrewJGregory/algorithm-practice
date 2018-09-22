# FIND MINIMUM IN ROTATED SORTED ARRAY

### High level idea

Since the array is somewhat sorted, binary search can be used to find the minimum element. The question then becomes how is the _minimum_ found? The minimum is the only element in the rotated sorted array such that `nums[i] > nums[i+1]`, that is, when the next element is _less than_ the previous element. This holds because the array is sorted so the elements should only be increasing. Determining whether to search left or right is a matter of if the first element of the left and right subarray is larger or smaller than mid. An example of that is `[10, 11, 12, 13, 14, 0, 1]`. Since 13 is larger than 10, the minimum must be somewhere to the right of the mid.

### Time and space complexity

Let `n` be the size of the array:

- Time: `O(log(n))` <br>
- Space: `O(1)` <br>

See the binary search explanation for a derivation of logarithmic time complexity.
