# DELETE NODE IN A LINKED LIST

### High level idea

Since access is not provided to the previous node, the given node cannot be removed by the traditional means of pointing its predecessor to the node after it. Instead, the final result needs to "look like" the node has been removed. The value from the next node can be copied into the current node, and then the current node can be pointed to the node _after_ the node that has been copied. Example:

Consider the linked list `1 -> 2 -> 3 -> 4 -> 5 -> 6 -> null` and given access to the node containing the value `3`, we want the list to look like: <br>
`1 -> 2 -> 4 -> 5 -> 6 -> null`

First, copy the given node's next value (in this case, `4`) into the given node. Now, the linked list looks like this: <br>
`1 -> 2 -> 4 -> 4 -> 5 -> 6 -> null`

This is closer to the final result, but still one step away. Now, the given node can be pointed to the next next node (the node containing the value `5`) to remove the duplicate, second `4` which gives the final answer.

### Time and space complexity

- Time: `O(1)` <br>
- Space: `O(1)`
