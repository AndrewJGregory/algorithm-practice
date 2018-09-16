# REMOVE DUPLICATES FROM SORTED LIST

### High level idea

Since the list is sorted and only one value needs to be kept, adjacent node's values can be checked for equality. If there is a duplicate, that node can be removed by pointing around it to the subsequent node. This process is continued until there are no more duplicates for that given value, then the pointer can be advanced to check for the next node. This continues until the end of the list is reached.

### Time and space complexity

Let `n` be the length of the linked list:

- Time: `O(n)` <br>
- Space: `O(1)`
