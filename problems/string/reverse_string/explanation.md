# REVERSE A STRING

### High level idea

Since strings are immutable in Javascript, we can't reverse the string in place. <br> 
We can split the string or build the string by iterating backwards.

### Time and space complexity

Let: <br>

- `n` be the size of the string

All cases: <br>

- Time: `O(n)`

Reversing a string requires us to always touch every character of the string. <br>
Therefore linear time complexity in all cases.