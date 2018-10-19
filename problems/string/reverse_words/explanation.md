# REVERSE WORDS IN A STRING

### High level idea

The fun of this problem comes from handling the constraints. Mainly, that the leading and trailing spaces must be omitted from the final answer along with there should be only once space between each word. There is a built-in `trim` method in JavaScript that removes the leading and trailing whitespace from a string, but it is more fun for this problem to try writing it by hand. The idea is to find the first non-space character index and the last non-space character index, then take a slice of the string from the two indices. Care must be taken to avoid the case of just spaces passed in (such as `" "`) because then neither index would be set and all of the spaces would be returned. The conditional in between the two loops handles just that: if the first non-space index is zero _and_ the first index is a space, then the entire string must be spaces.

As for reducing multiple spaces, the idea is to add non-space characters to a new string until a space is found. Once a space is found, then add that space onto the new string as long as the last character isn't a space. This is what eliminates the multiple spaces between words.

As for the primary algorithm, the string can be iterated from back to front, carefully reversing each word until a space is found. Once a space is found, add the reversed word to the new string.

// TODO: write reduce multiple spaces and primary algorithm in constant space.

### Time and space complexity

Let `n` be the length of the string:

- Time: `O(n)` <br>
- Space: `O(n)` <br>

The extra space comes from the "result" string. I feel like this can be done without declaring another variable, however it is impossible to do "in-place" in JavaScript because strings are immutable.
