# PASCALS TRIANGLE

### High level idea

The idea of "each number is the sum of the two numbers directly above it" needs to be translated into code. For any given number in any row, the "two numbers directly above it" are its index - 1 and its index in the previous row. For example, for the fifth row, to generate the element at index 1, numbers in indices 0 and 1 in the previous row must be added. (`4 = 1 + 3`). The only exceptions are the first and last numbers in any given row, which will always be `1`. There are two different ways to handle this:

- in the ruby solution, the leading and trailing one can be added before and after the inner row is constructed, respectively

- in the JS solution, the number can be checked to see if it is `undefined`. If it is, this means that the algorithm is either at the beginning or the end of the array.

### Time and space complexity

- Time: `O(numRows ^ 2)` <br>
- Space: `O(numRows ^ 2)` <br>

The outer loop happens `numRows` times and the inner loop happens `1 + 2 + 3 + 4 + ... + numRows` times, which sums to `numRows * (numRows+1)/2`. This reduces to the given time complexity. For space complexity, it is the same summation which gives the given space complexity.
