# REVERSE WORDS

### High level idea

Given the example "The eagle has landed" its a bit challenging to reverse the individual words since the words are a not the same length. <br>
What happens if we were to reverse the entire sentence by each character? <br>
We get "deadnal sah elgae ehT". That's pretty good actually, the words are in the right places, but reversed.

We need to go back one more time and reverse each word now.

A helper method that reverses a string in place with starting index and end index would be helpful here.<br>

### Time and space complexity

Let: <br>

- `n` be the size of the input array (in javascript we would need an array as strings are immutable)<br>

Since we reverse the entire string and go back for a second pass to reverse the words within the string. <br> We would have a time complexity of 
`O(2n)` which simplfies to `O(n)` which is reasonable as to reverse a string we need to touch every character.
