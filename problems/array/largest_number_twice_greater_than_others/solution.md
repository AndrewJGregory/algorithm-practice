# Largest Number At Least Twice of Others

```rb
def dominant_index(nums)
    max = nums.max
    max_idx = nums.index(max)
    nums.each do |num|
       next if num === max
       return -1 if (num * 2 > max)
    end
    max_idx
end
```

```js
var dominantIndex = function(nums) {
  const max = Math.max(...nums);
  const maxIndex = nums.indexOf(max);
  for (let i = 0; i < nums.length; i++) {
    const num = nums[i];
    if (i === maxIndex) continue;
    if (num * 2 > max) return -1;
  }
  return maxIndex;
};
```
