# PASCALS TRIANGLE KTH ROW

### High level idea

Same idea as the other Pascals Triangle solution. Instead, the current row is repeatedly re-assigned to avoid allocating so much memory to generate the entire triangle.

### Time and space complexity

Let `k` be the desired row of Pascals Triangle:

- Time: `O(k^2)` <br>
- Space: `O(k)` <br>

See the other pascals triangle solution for an explanation on the time complexity. As for the space complexity, two arrays are used which corresponds to `O(k-1)` + `O(k)` space, which is just `O(k)`.
