# BINARY TREE LEVEL ORDER TRAVERSAL

```rb
def level_order(root)
    return [] if root.nil?
    result = [[root.val]]
    nodes = [[root]]
    while true
        next_level_nodes = []
        next_level_vals = []
        nodes.last.each do |node|
            left = node.left
            right = node.right
            if left
                next_level_nodes << left
                next_level_vals << left.val
            end
            if right
                next_level_nodes << right
                next_level_vals << right.val
            end
        end
        break if next_level_nodes.empty?
        result << next_level_vals
        nodes << next_level_nodes
    end
    result
end
```

```js
var levelOrder = function(root) {
  if (!root) return [];
  const vals = [[root.val]];
  const nodes = [[root]];
  while (true) {
    const nextLevelNodes = [];
    const nextLevelVals = [];
    nodes[nodes.length - 1].forEach(node => {
      const left = node.left;
      const right = node.right;
      if (left) {
        nextLevelNodes.push(left);
        nextLevelVals.push(left.val);
      }
      if (right) {
        nextLevelNodes.push(right);
        nextLevelVals.push(right.val);
      }
    });
    if (nextLevelNodes.length === 0) break;
    vals.push(nextLevelVals);
    nodes.push(nextLevelNodes);
  }
  return vals;
};
```
