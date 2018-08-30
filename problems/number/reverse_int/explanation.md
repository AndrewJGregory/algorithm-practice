# REMOVE DUPLICATES FROM SORTED ARRAY

### High level idea

By doing some modulo math we can reverse the integer. <br>

Since the prompt is concerned about storing the number as 32-bit. <br>
We will check the reversed integer and make sure it is valid to be stored in a 32-bit environment.

In the case of a negative number we can store the sign and convert it to be positive. <br>
We can then perform the same operation and convert it to be negative after.

### Time and space complexity

Worst cases:

Let `n` be the size of the number. <br>

- Time: `O(log(n))` <br>
- Space: `O(1)`

In the worse case we will have to reverse the entire number, this is a log complexity with base 10. Simplifies to O(log(n)). <br>
We are only using a variable to store the reversed number, thus constant space complexity.
