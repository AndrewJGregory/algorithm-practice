# Largest Number At Least Twice of Others

## High level idea

First, the largest number must be found so every other number can be checked to see if when doubled, it exceeds the largest number. The index of the largest number is what will be returned. The first two lines of each solution could be done with one loop but it wouldn't impact the final time complexity at all. An important condition is to make sure to skip the largest number when checking to see if the double of any number exceeds the largest number.

## Time and space complexity

Let `n` be the length of nums:

- Time: `O(n)` <br>
- Space: `O(1)` <br>

There are three loops in each solution, each of which has a time complexity of `O(n)`. There is no additional space needed since every variable's size does not depend on `n`.
