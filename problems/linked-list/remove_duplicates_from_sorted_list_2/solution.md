# REMOVE DUPLICATES FROM SORTED LIST 2

```rb
def delete_duplicates(head)
    return head if head.nil?
    val = head.val
    while (head.next && val == head.next.val)
        while (head && val == head.val)
            head = head.next
        end
        val = head.val unless head.nil?
        return head if head.nil?
    end
    ptr = head
    fast = nil
    while (ptr.next)
        if (ptr.next.next && ptr.next.val == ptr.next.next.val)
            val = ptr.next.val
            fast = ptr.next
            while (fast && val == fast.val)
                fast = fast.next
            end
            ptr.next = fast
        else
            ptr = ptr.next
        end
    end
    head
end
```

```js
var deleteDuplicates = function(head) {
  if (!head) return null;

  let val = head.val;
  while (head.next && val === head.next.val) {
    while (head && val === head.val) {
      head = head.next;
    }
    if (head) {
      val = head.val;
    } else {
      return null;
    }
  }

  let ptr = head;
  while (ptr.next) {
    fast = ptr.next;
    val = fast.val;
    if (fast.next && fast.val === fast.next.val) {
      while (fast && val == fast.val) {
        fast = fast.next;
      }
      ptr.next = fast;
    } else {
      ptr = ptr.next;
    }
  }
  return head;
};
```
