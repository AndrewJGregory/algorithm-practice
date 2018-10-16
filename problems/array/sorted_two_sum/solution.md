# SORTED TWO SUM

```rb
def two_sum(numbers, target)
    leftIdx = 0
    rightIdx = numbers.length - 1
    while leftIdx < rightIdx
        leftNum = numbers[leftIdx]
        rightNum = numbers[rightIdx]
        if leftNum + rightNum == target
            return [leftIdx + 1, rightIdx + 1]
        elsif leftNum + rightNum > target
            rightIdx -= 1
        else
            leftIdx += 1
        end
    end
end
```

```js
var twoSum = function(numbers, target) {
  let left = 0;
  let right = numbers.length - 1;
  while (left < right) {
    const sum = numbers[left] + numbers[right];
    if (target === sum) {
      return [left + 1, right + 1];
    } else if (target < sum) {
      right--;
    } else {
      left++;
    }
  }
};
```
