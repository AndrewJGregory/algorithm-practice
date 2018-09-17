# BINARY SEARCH

### High level idea

Given a sorted collection and a target to search for, every element need not be checked to find if the target exists. The collection can be repeatedly cut in half and the middle element can be checked to determine the existence of a target. Here is an example with an array of integers and a target:

```
nums = [1,2,3,4,5,6,7,8,9]
target = 9
middle number is 5
target is greater than the middle, because the array is sorted. search the right half

right half is [6,7,8,9]
middle number is 7
target is greater than the middle, search right half again

right half is [8,9]
middle number is 8
target is greater than the middle, search right half again

right half is [9]
return index 0 because the middle number is the target. When the right half is searched, the change in index has to be accounted for because the intended index is 8 here, but 0 would be returned.
```

### Time and space complexity

Let `n` be the size of the input array:

- Time: `O(log(n))` <br>
- Space: `O(1)` <br>

One way to think of logarithmic time complexity is that not every element needs to be checked whereas in linear time complexity every single element is checked. More formally, consider the above example:

```
nums = [1,2,3,4,5,6,7,8,9] length = 8
nums = [6,7,8,9] length = 4
nums [8,9] length = 2
nums = [9] length = 1
```

The question is how many steps does the algorithm have to take to terminate. The length can be thought of as doubling instead of halving, such as `1 => 2 => 4 => 8`. How many times does this happen? Let `k` be the amount of steps.

```
2^k = n
k = log n
```

This is where logarithmic time complexity comes from.
