# REVERSE SINGLY LINKED LIST

### High level idea

There are four steps to reverse a singly linked list. First, a reference to the next node must be saved. This is due to once the current node is pointed back, the reference to the next node is lost. Second, the current node can be pointed "back", thereby reversing a small portion of the linked list. Third, the "previous" node has to be advanced so the next current node can be pointed at that node. Finally, the node doing the pointing has to be advanced so the list can continue to be traversed. This process continues until the end of the list is reached, which is denoted by `null`, `nil`, etc.

Consider the singly linked list `1 -> 2 -> 3 -> 4 -> 5 -> nil`. The reversed singly linked list is `5 -> 4 -> 3 -> 2 -> 1 -> nil`. `head` is the node containing the value `1`. Here is the annotated ruby iterative solution:

```rb
def reverse_list(head)
  prev = nil # use this value to point back to
  current = head # use this value to do the pointing
  after = nil # use this value to save the reference to the next node
  until current.nil?
    after = current.next
    # save the reference to the next node, 2
    current.next = prev
    # this points 1 back at nil. Now, there are two singly linked lists in memory:
    # 1 -> nil (current -> prev)
    # 2 -> 3 -> 4 -> 5 -> nil (after -> after.next -> after.next.next -> ...)
    prev = current
    # this answers the question "what should the next node point back to?" 2 should point back at 1, so prev is advanced
    current = after
    # this answers the question "what node should be doing the pointing?" what should point back at 1? It's 2, so current is advanced
  end
  return prev
end
```

### Time and space complexity

Worst cases:

Let `n` be the length of the singly linked list. <br>

- Time: `O(n)` <br>
- Space: `O(1)`

The size of variables is not dependent on the size of the input. The entire list needs to be traversed so the time complexity reflects this.
