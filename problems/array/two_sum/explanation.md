# TWO SUM

### High level idea

We could brute force and compare each index against another to see if the value of their sum equals the target. <br>
This would give us a `O(n`<sup>`2`</sup>`)` time complexity where n is the length of the array and we can definitely do better than that. <br>

The better solution takes advantage of using a hash data structure. We can store a seen number as the key and its corresponding index as the value. <br>
As we iterate through the array we need to ask ourself if we had seen (target - current_val), this information is conviently stored in our hash along with the index. <br>
We would simply return our current index, and the value (which is the index) of the complimentary number found in our hash.

### Time and space complexity

Worst cases:

Let `n` be the size of the input array. <br>

- Time: `O(n)` <br>
- Space: `O(n)` <br>

The array may not have any combinations of sums that equal the target. <br>
In this case we would have iterated through the entire array and stored all of its values with corresponding indicies in our hash. <br>
Thus, a linear time complexity with a linear space complexity.