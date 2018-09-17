# REMOVE DUPLICATES FROM SORTED LIST 2

### High level idea

There are two processes for removing duplicates and both of them are different depending on where the duplicates occur. First, removing nodes from the middle of the list is **not** the same process as removing nodes from the very beginning of the list. To remove nodes from the middle of the list, the duplicated nodes can be "pointed around", thereby removing them from the list. However, if the head and subsequent nodes are duplicates, then the head needs to be mutated and constantly reassigned until a different value is found.

These two approaches form the foundation of the solution. First, check if there are duplicate nodes in the beginning of the list. Save the first node's value and continually reassign the head to the next value until there a node's value is found that differs from the original, duplicated value. This process may need to be repeated, for example in the case of `1 -> 1 -> 1 -> 2 -> 2 -> 3`, after removing the first three `1`'s, the list becomes `2 -> 2 -> 3` and the process needs to be repeated again because the list starts with duplicates. This is why the first outer loop is necessary. Once duplicated nodes from the beginning are removed, then duplicates can begin to be found in the middle of the list. If there are duplicates ahead, then continually iterate until a node is found that is not a duplicate, so the duplicated nodes can be pointed around. In the case of `1 -> 2 -> 2 -> 2 -> 3`, the pointer would be pointing at `1`, and a new pointer (designated as fast) would be advanced until there is a node that doesn't have the value of `2`, in this case the node of `3`. Now, the first node can be pointed at node of `3`, removing the duplicated nodes.

### Time and space complexity

Let `n` be the length of the linked list:

- Time: `O(n)` <br>
- Space: `O(1)` <br>

At worst, if every node is a duplicate, then the entire length of the list needs to be iterated.
