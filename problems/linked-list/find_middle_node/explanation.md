# FIND MIDDLE NODE

### High level idea

One approach is to find the length of the list first then iterate one pointer half of the linked list's length to find the middle node. Instead, two pointers can be used such that the `fast` pointer advances 2 nodes for every 1 node the `slow` pointer advances. In this way, the `slow` pointer will always end up at the middle node because when `fast` is `null` (in the case of an even length list) or `fast.next` is null (in the case of an odd length list).

### Time and space complexity

Let `n` be the length of the linked list:

- Time: `O(n)` <br>
- Space: `O(1)` <br>

The loop will iterate for `n/2` iterations which is reduces to `n`.
