# PREORDER TRAVERSAL

## RECURSIVE

```rb
def preorder_traversal(root)
ans = []
    if root
        ans.push(root.val)
        ans = ans.concat(preorder_traversal(root.left))
        ans = ans.concat(preorder_traversal(root.right))
    end
    return ans
end
```

```js
var preorderTraversal = function(root) {
  const vals = [];
  if (root) {
    vals.push(root.val);
    vals.push(...preorderTraversal(root.left));
    vals.push(...preorderTraversal(root.right));
  }
  return vals;
};
```

## ITERATIVE

```rb
def preorder_traversal(root)
    ans = [root]
    vals = []
    until ans.empty?
        popped = ans.pop
        if popped
            vals.push(popped.val)
            ans.push(popped.right)
            ans.push(popped.left)
        end
    end
    return vals
end
```

```js
var preorderTraversal = function(root) {
  const vals = [];
  const nodes = [root];
  while (nodes.length) {
    const popped = nodes.pop();
    if (popped) {
      vals.push(popped.val);
      nodes.push(popped.right);
      nodes.push(popped.left);
    }
  }
  return vals;
};
```

```

```
