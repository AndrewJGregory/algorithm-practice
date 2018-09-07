# ROTATE MATRIX

### High level idea

When looking at the rotated matrix, it _almost_ looks like it has been transposed. The only difference is that the answer has rows that have been reversed from its transposed counterpart. The solution is to transpose the matrix in place and then reverse each row in place, both of which use constant space extra memory.

### Time and space complexity

Let `n` be the length of the rows and columns in the matrix: <br>

- Time: `O(n^2)` <br>
- Space: `O(1)` <br>

Reducing the time complexity for transforming a matrix in place comes out to `O(n^2)` even though the second loop starts at `i` instead of `0`. The outer loop runs `n` times while the inner loop runs `n - 1`, `n - 2`, etc times until 0. The constants in `n - 1`, `n - 2`, etc can be dropped such that the total time complexity is quadratic. Reversing every row in the matrix in place is also `O(n^2)` since for _every_ row, half of it must be iterated to reverse it. Therefore, the total time complexity for this algorithm is `O(n^2)`.
