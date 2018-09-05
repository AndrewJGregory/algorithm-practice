# ROTATE ARRAY

### High level idea

From looking at the examples, it looks the last `k` elements are inserted into the front of the array. Since the array has to be mutated in place, "dangerous" methods have to be used. One idea is to repeatedly pop elements off of the end while unshifting them. Another is to delete and save the last `k` elements to insert them onto the front.

### Time and space complexity

Time: `O(k)` <br>
Space: `O(1)` <br>

Unshifting's time complexity depends on the language's implementation of it, but it is relatively safe to say that it is amortized constant time. `k` is the input. An optimization is to modulo k by the length of the numbers array since rotating more than how many numbers there are is repeated work. If an array is 5 elements and the array is rotated 5 times, the same exact array is returned.
