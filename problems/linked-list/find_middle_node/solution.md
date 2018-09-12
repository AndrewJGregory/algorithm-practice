# FIND MIDDLE NODE

```rb
def middle_node(head)
    slow = head
    fast = head
    until fast.nil? || fast.next.nil?
        slow = slow.next
        fast = fast.next.next
    end
    slow
end
```

```js
var middleNode = function(head) {
  let slow = head;
  let fast = head;
  while (fast !== null && fast.next !== null) {
    slow = slow.next;
    fast = fast.next.next;
  }
  return slow;
};
```
