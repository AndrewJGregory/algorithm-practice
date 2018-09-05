# ROTATE ARRAY

```rb
def rotate(nums, k)
    k %= nums.length
    k.times { nums.unshift(nums.pop) }
end
```

```js
var rotate = function(nums, k) {
  const last = nums.splice(nums.length - k, k);
  nums.splice(0, 0, ...last);
};

var rotate = function(nums, k) {
  k %= nums.length;
  for (let i = k; i > 0; i--) nums.unshift(nums.pop());
};
```
