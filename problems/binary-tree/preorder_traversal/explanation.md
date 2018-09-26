# PREORDER TRAVERSAL

## High level idea

Preorder traversal of a tree is to visit the root first, then traverse the left subtree, then traverse the right subtree. For a tree like this:

```
    1
  /   \
  2    3
 / \  / \
4  5  6 7
```

The preorder traversal would be `1, 2, 4, 5, 3, 6, 7`.

A stack is needed in both the recursive and iterative implementations. Recursively, the call stack serves as the stack to hold the values. Iteratively, an explicit array keeps track of the current nodes.

### Recursive Solution Walkthrough

Step by step, function call by function call, this is what the recursive solution for ruby would look like:

frame one:
<br>root = node 1<br>
ans = [1] <br>
preorder traversal gets called on root.left which is node 2, so another frame is added to the stack <br><br>
frame two: <br>root = node 2<br>
ans = [2]<br>
preorder traversal gets called on root.left which is node 4, so another frame is added to the stack <br><br>
frame three: <br>root = node 4<br>
ans = [4]<br>
preorder traversal gets called on root.left which is nil, so another frame is added to the stack<br><br>
frame four: root = nil
an empty array is returned, and now we return to frame three. This frame is popped off of the stack.

---

frame three had ans = [4], now preorder traversal gets called on root.right which is nil, so another frame is added to the stack

frame four: root = nil
an empty array is returned, and now we return to frame three. This frame is popped off of the stack.

---

frame three has now finished all of the statements within the conditional. It returns `ans`, which is `[4]`. This frame is now popped off of the stack, and returns its value to frame two.

---

frame two had ans = [2], and now `ans = ans.concat(preorder_traversal(root.left))` is done. <br> The result of the right was `[4]`, so now ans = [2,4]. <br>Now, the program goes to the next line, `ans = ans.concat(preorder_traversal(root.right))`. <br>In this frame, the node has the value of 2. <br>preorder_traversal gets called on root.right which is node 5, so another frame is added to the stack.<br>

frame three: <br>root = 5<br>
ans = [5]<br>
<br>again, the preorder_traversal would get called on the left and right of this node, but both would be nil so see above for the in-depth explanation of that when node 4's left and right was nil.<br>

---

frame three has now finished all of the statements into the conditional and now returns [5] to frame two. <br>`ans` in frame two was [2,4], now it becomes [2,4,5]. <br>Frame two has now finished all of its statements in the conditional, and ultimately returns [2,4,5] to the first frame.

---

frame one was only computing `ans = ans.concat(preorder_traversal(root.left))`. <br>`ans` is now [1,2,4,5] because of the traversing done above. <br>Next, `ans = ans.concat(preorder_traversal(root.right))` is executed and the entire process above is repeated for the right half of the tree.

(Walk through this process for the right half of tree at this point yourself and see if you understand it.)

### Iterative Solution Walkthrough

For the iterative solution, the left node is added last because the left subtree must be visited first before the right subtree.

## Time and space complexity

Let `n` be how many nodes are in the tree:

- Time: `O(n)` <br>
- Space: `O(n)` <br>

Every node needs to be touched in order to traverse the entire tree. In the recursive solution, the call stack takes up `O(n)` space, and in the iterative solution, the space is more explicit because of the array that functions as a stack.
