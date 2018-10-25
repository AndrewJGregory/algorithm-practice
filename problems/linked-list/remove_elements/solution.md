# REMOVE ELEMENTS FROM SINGLY LINKED LIST

```rb
def remove_elements(head, val)
  head = head.next while head && head.val == val
  ptr = head
  while ptr && ptr.next
      if ptr.next.val == val
          ptr.next = ptr.next.next
      else
          ptr = ptr.next
      end
  end
  head
end
```

```js
var removeElements = function(head, val) {
  while (head && head.val === val) head = head.next;
  let ptr = head;
  while (ptr && ptr.next) {
    if (ptr.next.val === val) {
      ptr.next = ptr.next.next;
    } else {
      ptr = ptr.next;
    }
  }
  return head;
};
```
