# BINARY TREE LEVEL ORDER TRAVERSAL

### High level idea

The example given is misleading because the last two levels have two nodes each, which is not always the case. Consider this example:

```
   3
 /   \
 9   20
/ \  / \
1 2 15  7
```

The expected traversal is

```
[
  [3],
  [9,20],
  [1,2,15,7]
]
```

If all of the last level of nodes had children, then there would be eight nodes in the last level. This thought process helps discover the solution because for every next level, the previous level needs to be iterated over and its non-null children are added to the next level. A level's iteration is from left to right, gathering the left _and_ right children values.

The traversal is finished if the next level (all of the previous level node's children) are `null`. This means that the bottom of the tree has been reached and the values can be returned.

Note: It is possible to avoid the two arrays, one for the nodes and one for the final values array. However, that code is a lot less readable because it involves mapping the last level's nodes to their values before iterating over again. I think the two way array approach is much easier to understand and the additional array does not increase space complexity.

### Time and space complexity

Let `n` be the amount of nodes in the tree:

- Time: `O(n)` <br>
- Space: `O(n)` <br>

Every node in the tree is going to be iterated over since all values will be in the final array, so the time complexity is `O(n)`. The length and size of the final array of values is dependent on how many nodes there are as well.
