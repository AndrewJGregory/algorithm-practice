# SEARCH IN SORTED ROTATED ARRAY

### High level idea

Since the array is rotated, there are two cases to consider:

- Case 1: `[9, 11, 12, 13, 1, 2, 3, 4, 5]` <br>
- Case 2: `[2, 3, 4, 5, 9, 11, 12, 13, 1]` <br>

The array is, in a sense, sorted so binary search can be used to find the target number. However, the array isn't sorted in a traditional manner because the minimum isn't the first element and the maximum isn't the last element. (Nor is the maximum at the beginning and the minimum at the end). These two cases help to consider the two possibilities of either the left half or the right half is sorted as expected.

In case 1, the middle element is `1`. Checking the last element of the array to see if it is greater than the middle will tell if the right half is sorted. After figuring out that the right half is sorted, check if the target is actually within that range. This is necessary because if the target is greater than 5 (the last element), then if it does exist, it will be in the left half of the array due to the rotated nature of the array. The right half is `[1,2,3,4,5]`.

In case 2, the left half is sorted. The middle element is 9, and the left half is `[2,3,4,5,9]`. Again, the beginning and end of this half is checked to see if the target can exist in that range. If the target falls outside of the range 2 through 9, then it must be in the other half of the array if it were to exist at all.

This process is repeated until the element is found or until there are no more halves to consider.

### Time and space complexity

Let `n` be the length of the given array:

- Time: `O(log(n))` <br>
- Space: `O(1)` <br>

See the binary search explanation for a derivation of logarithmic time complexity.
