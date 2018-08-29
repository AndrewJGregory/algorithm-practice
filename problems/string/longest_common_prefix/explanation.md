# LONGEST COMMON PREFIX

### High level idea

Pick the first word to iterate through and keep taking a substring from the beginning of it, checking that substring against all of the other words in the array. Only if _all_ of the words in the string have a prefix that matches that substring should the loop continue. Otherwise, there is no longer a common prefix so the loop can stop checking further prefixes to return the longest prefix found so far.

### Time and space complexity

Let: <br>

- `n` be the size of the input array <br>
- `m` be the size of one of the strings in the array

Worst cases: <br>

- Time: `O(n * m)` <br>
- Space: `O(1)`

The worst case happens when all of the strings in the array are substrings of each other: they are all the same word. In this case, the algorithm would iterate through the _entire_ word checking every single prefix substring against _every_ other string in the array. Since every word is the same, both loops would continue until the very end and not terminate early. Note that `n` and `m` are unrelated and therefore cannot be simplified. An example of a worst case is `["flower", "flower", "flower"]`. The space complexity is constant since there is no new allocation of memory relative to the input.

### Edge cases missed

If the array is empty (early return statement handles this) and if there was an array of just the empty string `[""]`, (last line of return statement handles this because if the first str is length 0 as per the emtpy string, the loop would never execute). I initally had the last return statement but removed it because I didn't see a reason when the loop wouldn't execute. Empty array input is pretty common but I missed that. Another edge case that is covered is what if there is only one word in the input array? Then the entire word is a substring. This is handled because the algorithm checks for _all_ words in the array if the prefix matches rather than excluding the first word and checking all of the other words.
