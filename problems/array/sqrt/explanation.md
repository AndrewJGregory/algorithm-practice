# SQUARE ROOT

### High level idea

This question is asking for the integer square root of a number. To find it in logarithmic time instead of linear time, binary search can be used to repeatedly halve the search space. The integer square root of a number, `n`, is defined as the largest `x` such that `x * x <= n && (x + 1) * (x + 1) > n`. A guess can be made and then checked to see if it is the answer or if its square is greater than n. If its square is greater, than the maximum of the search space can be reduced by 1.

### Time and space complexity

Let `n` be the given number:

- Time: `O(log(n))` <br>
- Space: `O(1)` <br>

See the binary search explanation for a derivation of logarithmic time complexity.
