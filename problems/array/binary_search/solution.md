# BINARY SEARCH

## ITERATIVE

```rb
def search(nums, target)
    return -1 if nums.nil? || nums.empty?
    left = 0
    right = nums.length - 1
    while left <= right
        mid = (left + right)/ 2
        if nums[mid] == target
            return mid
        elsif nums[mid] < target
            left = mid + 1
        else
            right = mid - 1
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
    let mid = Math.floor((left + right) / 2);
    if (nums[mid] === target) {
      return mid;
    } else if (nums[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }
  return -1;
};
```

## RECURSIVE

```rb
return -1 if nums.empty?
    midIdx = nums.length/2
    mid = nums[midIdx]
    if mid == target
        return midIdx
    elsif mid < target
        idx = search(nums[midIdx+1..-1], target)
        return -1 if idx == -1
        return idx + midIdx + 1
    else
        return search(nums[0...midIdx], target)
    end
```

```js
var search = function(nums, target) {
  if (nums.length === 0) return -1;
  const midIdx = Math.floor(nums.length / 2);
  const middle = nums[midIdx];
  if (middle === target) {
    return midIdx;
  } else if (middle < target) {
    const right = nums.slice(midIdx + 1);
    const result = search(right, target);
    if (result === -1) return -1;
    return midIdx + result + 1;
  } else {
    const left = nums.slice(0, midIdx);
    return search(left, target);
  }
};
```
