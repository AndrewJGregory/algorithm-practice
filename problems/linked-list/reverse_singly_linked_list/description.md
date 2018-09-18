# REVERSE SINGLY LINKED LIST

Example:

```
Input: 1->2->3->4->5->NULL
Output: 5->4->3->2->1->NULL
```

Hints:

Only give hints if the person is really, really struggling and doesn't seem to be on the right track. Don't give all of the hints, but one at a time.

- On the first iteration, what do you want to set the first node's `.next` to? What happens when you do this? (answer: you want to set 1 -> null, but then you lose access to the next node and consequently the rest of the list)
- What can you do to counteract losing the next node? (answer: save it in another variable)
- On the next iteration, what do you want to point `2` at? (answer: the node `1` which now points to `null`)
