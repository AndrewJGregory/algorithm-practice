# FIRST BAD VERSION

### High level idea

One way to approach this problem is to search from the very first version to the `n`th version and see which is literally the first bad version. However, this is linear time complexity because every element would need to be checked in the worst case that the bad element is nearer toward `n`. A better approach is to use a variant of binary search and repeateadly look for an element such that it is "good" (`isBadVersion` returns false) and the subsequent element is "bad" (`isBadVersion` returns true). Considering this approach, there are three cases to consider:

1. false, false, false, true, true
2. false, true, true, true, true
3. false, false, false, false, true

In the first case, when the middle element is picked and the subsequent element is checked, the function immediately returns the subsequent number as the first bad version. However, in the second case, both versions are bad so the first bad version must have happened earlier. As such, the left half is searched to find the _first_ bad version. In the last case, both versions are good, so if there is a bad version it must have happened later on. Thus, the right half is searched.

Left is returned at the very end in the case that there is only one bad version (n = 1).

### Time and space complexity

Let `n` be the number that is given:

- Time: `O(log(n))` <br>
- Space: `O(1)` <br>

See the binary search explanation for a derivation of logarithmic time complexity.
