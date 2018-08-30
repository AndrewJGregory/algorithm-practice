# TWO SUM

```rb
def two_sum(nums, target)
  seen = {};
  nums.each_with_index do |val, idx|
    comp_val = target - val
    if seen.has_key?(comp_val)
      return [seen[comp_val], idx]
    else
      seen[val] = idx
    end
  end
  []
end
```

```js
function twoSum(nums, target) {
  const seen = {};

  for (let i = 0; i < nums.length; i++) {
    const currentVal = nums[i];
    const compIdx = seen[target-currentVal];

    if (compIdx > -1) { // index of 0 is falsy
      return [compIdx, i];
    } else {
      seen[currentVal] = i;
    }
  }

  return [];
}
```
