# MOVE ZEROES

```rb
def move_zeroes(nums)
    i = 0
    timesExecuted = 0
    while i < nums.length && timesExecuted < nums.length
      nums[i].zero? ? nums.push(nums.delete_at(i)) : i += 1
      timesExecuted += 1
    end
end
```

```js
var moveZeroes = function(array) {
  let timesExecuted = 0;
  let i = 0;
  while (i < array.length && timesExecuted < array.length) {
    array[i] === 0 ? array.push(array.splice(i, 1)[0]) : i++;
    timesExecuted++;
  }
};
```
