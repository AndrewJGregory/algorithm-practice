# REMOVE NTH NODE FROM END

# ITERATIVE

```rb
def remove_nth_from_end(head, n)
    fast = head
    n.times { fast = fast.next }

    return head.next if fast.nil?

    slow = head
    until fast.next.nil?
      slow = slow.next
      fast = fast.next
    end
    slow.next = slow.next.next
    head
end
```

```js
var removeNthFromEnd = function(head, n) {
  let fast = head;
  let slow = head;
  for (let i = 0; i < n; i++) fast = fast.next;

  if (fast === null) return head.next;

  while (fast.next) {
    slow = slow.next;
    fast = fast.next;
  }

  slow.next = slow.next.next;
  return head;
};
```

# RECURSIVE

```rb
def remove_nth_from_end(head, n, fast = nil, slow = nil)
    if n.zero?
      return head.next if fast.nil?
      slow = slow || head
      if !fast.next.nil?
        slow = slow.next
        fast = fast.next
        return remove_nth_from_end(head, 0, fast, slow)
      else
        slow.next = slow.next.next
        return head
      end
    end
    fast = fast || head
    fast = fast.next
    remove_nth_from_end(head, n - 1, fast, nil)
end
```

```js
var removeNthFromEnd = function(head, n, fast = null, slow = null) {
  if (n === 0) {
    if (fast === null) return head.next;
    slow = slow || head;
    if (fast.next !== null) {
      slow = slow.next;
      fast = fast.next;
      return removeNthFromEnd(head, 0, fast, slow);
    } else {
      slow.next = slow.next.next;
      return head;
    }
  }
  fast = fast || head;
  fast = fast.next;
  return removeNthFromEnd(head, --n, fast, slow);
};
```
