# MAX CONSECUTIVE ONES

### High level idea

This is a great example of the "best so far" technique. The streaks of 1s are counted until a 0 is encountered, then the current streak is compared against the best streak. If the current streak is longer, then update the best streak. The last line is needed because if the best streak terminates the array (such as `[1, 0, 1, 1, 1, 1, 1]` or the entire array being 1s), then the best streak would never get set because a 0 is never encountered _after_ the streak.

### Time and space complexity

Let `n` be the size of the input array:

- Time: `O(n)` <br>
- Space: `O(1)` <br>
