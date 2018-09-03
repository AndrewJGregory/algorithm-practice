# DELETE NODE IN A LINKED LIST

```rb
def delete_node(node)
    node.val = node.next.val
    node.next = node.next.next
end
```

```js
var deleteNode = function(node) {
  node.val = node.next.val;
  node.next = node.next.next;
};
```
