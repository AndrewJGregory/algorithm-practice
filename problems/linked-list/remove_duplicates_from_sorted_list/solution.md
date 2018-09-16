# REMOVE DUPLICATES FROM SORTED LIST

```js
var deleteDuplicates = function(head) {
  return null if (!head);
  let ptr = head;
  while (ptr.next) {
    if (ptr.val === ptr.next.val) {
      ptr.next = ptr.next.next;
    } else {
      ptr = ptr.next;
    }
  }
  return head;
};
```

```rb
def delete_duplicates(head)
  return nil if head.nil?
  pointer = head
  until pointer.next.nil?
    if pointer.val == pointer.next.val
      pointer.next = pointer.next.next
    else
      pointer = pointer.next
    end
  end
  return head
end
```
