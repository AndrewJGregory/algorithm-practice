# SEARCH IN SORTED ROTATED ARRAY

```rb
def search(nums, target)
    left = 0
    right = nums.length - 1
    while left <= right
      first = nums[left]
      midIdx = (left + right)/2
        mid = nums[midIdx]
        last = nums[right]
        return midIdx if mid == target
        if mid < last # right half is sorted
            if mid < target && target <= last
                left = midIdx + 1
            else
                right = midIdx - 1
            end
        else # left half is sorted
            if first <= target && target < mid
                right = midIdx - 1
            else
                left = midIdx + 1
            end
        end
    end
    -1
end
```

```js
var search = function(nums, target) {
  let left = 0;
  let right = nums.length - 1;
  while (left <= right) {
    let first = nums[left];
    let last = nums[right];
    let midIdx = Math.floor((left + right) / 2);
    let mid = nums[midIdx];
    if (mid === target) return midIdx;
    if (first <= mid) {
      if (first <= target && target < mid) {
        right = midIdx - 1;
      } else {
        left = midIdx + 1;
      }
    } else {
      if (target <= last && mid < target) {
        left = midIdx + 1;
      } else {
        right = midIdx - 1;
      }
    }
  }
  return -1;
};
```
