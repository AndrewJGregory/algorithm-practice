# GUESS NUMBER

### High level idea

Given the pre-defined API, this sounds like a question where binary search can be used instead of checking every single number from `1` to `n`. The search space is `1` to `n`. The middle number can be guessed, and depending on whether that guess is higher or lower than the actual answer, guess the middle number of lower than that or higher than that.

Suppose the answer is `n - 1`. The first few guesses would be as follows: `n/2 => 3/4 * n => 7/8 * n => ...`

### Time and space complexity

Let `n` be the `n` input:

- Time: `O(log(n))` <br>
- Space: `O(1)` <br>

See the binary search explanation for a derivation of logarithmic time complexity.
