# REMOVE ELEMENTS FROM SINGLY LINKED LIST

### High level idea

There are two distinct cases to consider. First, a node containing the `val` occurs at the very start of the list. In this case, the removal process is significantly different than removing the a node with the `val` in the middle of the list. The `head` needs to be constantly re-assigned as long as it has a value equal to `val`. Once this is done, then the rest of the list can be checked to see if any other nodes have values that equal `val`. To remove these, the previous node can be pointed around the next node that has a value equal to `val`. Notice the handling of the edge case if the head is `null`/`nil`: the `&&`s would short-circuit, both loops would never run, no errors would be thrown, and `null`/`nil` would be returned. The second loop needs the && in case the list is all values that equal `val` because then every node would be removed and `head` would equal `null`/`nil`.

### Time and space complexity

Let `n` be the length of the linked list:

- Time: `O(n)` <br>
- Space: `O(1)` <br>

Every node in the list needs to be checked to see if it has to be removed, so the time complexity is linear.
