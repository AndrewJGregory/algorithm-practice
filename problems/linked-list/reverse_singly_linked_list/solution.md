# REVERSE SINGLY LINKED LIST

## RECURSIVE

```rb
def reverse_list(head, prev = nil)
    return prev if head.nil?
    after = head.next
    head.next = prev
    prev = head
    head = after
    reverse_list(head, prev)
end
```

```js
var reverseList = function(head, prev = null) {
  if (head === null) return prev;
  let after = head.next;
  head.next = prev;
  prev = head;
  return reverseList(after, prev);
};
```

## ITERATIVE

```rb
def reverse_list(head)
  prev = nil
  current = head
  after = nil
  until current.nil?
    after = current.next
    current.next = prev
    prev = current
    current = after
  end
  return prev
end
```

```js
var reverseList = function(head) {
  let prev = null;
  let current = head;
  let next = null;
  while (current) {
    next = current.next;
    current.next = prev;
    prev = current;
    current = next;
  }
  return prev;
};
```
