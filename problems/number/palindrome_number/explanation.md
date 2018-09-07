# CHECK IF NUMBER IS A PALINDROME

### High level idea

Since we have the restriction where we cannot convert the number into a string and reverse it to check we need to come up with a more clever solution. <br>
Let's consider some edge cases, in the given examples if a number is negative it can never be a palindrome. All negative numbers are asymmetrical. <br>
Also if a number ends in 0 than the only way the number can be a palindrome is if the number IS 0.

Now for all other cases, we could reverse the number doing some math using modulos. However, we need to make sure that the reverse of the number is within the bounds
of the maximum safe number. <br> `Number.MAX_SAFE_INTEGER` in JS.

What we could do is reverse the number halfway and check if the two halves are equal. <br>
How do we know when we have gone halfway? Simple, if the reversed number is greater than the moduloed.

We still need to consider some cases.

1. When the length of the number is odd eg. 11211 <br>
We would need to ignore the middle number, "2" in this case. <br>
Therefore when we finish finding the reversed numbers we need to add in an extra check in case we have an odd lengthed number

### Time and space complexity

Worst cases:

Let `n` be the size of the number. <br>

- Time: `O(log(n))` <br>
- Space: `O(1)` <br>

We have constant space as we just need a variable to store the reversed number. For time complexity we are simply dividing the number by 10 every time. <br>
We only do this calculation until we reach the half length of the number, however that is still a big-O of log(n).
