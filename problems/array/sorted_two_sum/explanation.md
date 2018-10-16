# SORTED TWO SUM

### High level idea

Since the array is sorted, every number does not need to checked against every other number, which would result in a quadratic time complexity. Instead, two pointers can be used, one starting at the front of the array and one at the end of the array. The number in the front of the array and the number in the end of the array can be added and checked against the target. If the sum is too large, the right pointer can be moved toward the left because this _guarantees_ a smaller sum due to the array being sorted. If the sum is too small, the left pointer can be moved toward the right because this _guarantees_ a larger sum due to the array being sorted. With these ideas in mind and adjusting for the "non-zero based" constraint of the solution, the solution can be implemented.

### Time and space complexity

Let `n` be the size of the input array:

- Time: `O(n)` <br>
- Space: `O(1)` <br>

The easiest way to understand this is to consider if the two numbers that add up to the target are in the center of the array. In this case, each pointer would be moved until they are pointing at each number that would produce the target sum. Therefore, the loop will execute at most `n - 1` times, which is `O(n)`. The loop will never run exactly `n` times because there is a guaranteed solution and eventually it will be found. (Not important for time complexity, but intriguing nonetheless.)
