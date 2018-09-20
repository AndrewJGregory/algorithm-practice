# VALID PERFECT SQUARE

### High level idea

This is a perfect use case for binary search because the numbers from `0` to `num` are sorted and the search space can be divided in half each time. The stopping condition is when the guessed number multiplied by itself is equal to the given num. If this does not eventually happen then the number cannot be a perfect square and the algorithm returns false. If the guessed number's square is smaller than the number, then if a perfect square does exist, it must be greater than the guessed number, so search the right half of the remaining search space.

### Time and space complexity

Let `num` be the given number:

- Time: `O(log(n))` <br>
- Space: `O(1)` <br>

See the binary search explanation for a derivation of logarithmic time complexity.
