# FIND MINIMUM IN ROTATED SORTED ARRAY

```rb
def find_min(nums)
    return nums.first if nums.first < nums.last
    left = 0
    right = nums.length - 1
    while left < right
        midIdx = (left + right)/2
        mid = nums[midIdx]
        after = nums[midIdx + 1]
        if mid > after
            return after
        elsif mid < nums[left]
            right = midIdx
        else
            left = midIdx + 1
        end
    end
    return nums[left]
end
```

```js
var findMin = function(nums) {
  if (nums[0] < nums[nums.length - 1]) return nums[0];
  if (nums.length === 0) return null;
  let left = 0;
  let right = nums.length - 1;
  while (left < right) {
    let midIdx = Math.floor((left + right) / 2);
    let mid = nums[midIdx];
    let after = nums[midIdx + 1];
    let first = nums[left];
    if (after < mid) {
      return after;
    } else if (first < mid) {
      left = midIdx + 1;
    } else {
      right = midIdx;
    }
  }
  return nums[left];
};
```
