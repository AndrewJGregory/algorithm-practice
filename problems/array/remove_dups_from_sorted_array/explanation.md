# REMOVE DUPLICATES FROM SORTED ARRAY

### High level idea

Since the array is sorted, the algorithm does not have to look far ahead for duplicates because if there are duplicates then they will be right next to each other. Iterate through the entire array and check if two adjacent numbers are the same. If they are then mutate the array to delete one of the numbers, being mindful that if the array does get mutated then the counter variable stays the same so it does not skip a number.

### Time and space complexity

Worst cases:

Let `n` be the size of the input array. <br>

- Time: `O(n)` <br>
- Space: `O(1)`

If the array has no duplicates then the loop will still execute for the length of the array, although no code will actually execute inside of the loop.
