# REMOVE NTH NODE FROM END

### High level idea

The tricky part about this problem is if the list is traversed, when is it known that the `nth` node from the end is being considered? If the length of the list is known, then the list can be traversed `length - n - 1` times so that that node's pointer can be changed to two nodes ahead, so the next node (the `nth` node from the end) is removed. Instead, two pointers can be used, denoted by `fast` and `slow`. The `fast` pointer gets a head start by `n` times, then both pointers iterate together at the same speed. Since a linked list's end is a `null` node, when the fast pointer's next node is `null`, then the `fast` pointer is the very last node in the list. Due to the `slow` pointer being `n` nodes behind, the `slow` pointer is the node _right_ before the `nth` node from the end. Therefore, the `nth` node can be removed. One edge case to be aware of is if `n` is the length of the list, which means that the very first node needs to be removed. This happens if `fast` starts traversing and ends up being `null`, which means that the entire list was traversed. In this special case, the `head`'s next node can be returned which effectively removes the first node in the list.

### Time and space complexity

Let `m` be the length of the linked list. <br>

- Time: `O(m)` <br>
- Space: `O(1)` <br>

The entire list will always be traversed. First, if the input `n` is the length of the linked list, then fast will iterate throughout the entire list and the first node will be removed. This is `m` steps, so the time complexity is `O(m)`. But if `n` < `m`, the total time complexity is _still_ `O(m)` because fast gets a head start, which is `n` steps. Then, fast and slow are iterated, which is `m - n` steps. `O(n + m - n)` reduces to `O(m)`.
