# REMOVE DUPLICATES FROM SORTED ARRAY

```rb
def remove_duplicates(nums)
    i = 0
    while i < nums.length
      if (nums[i] == nums[i+1])
        nums.delete_at(i)
      else
        i += 1
      end
    end
   return nums.length
end
```

```js
function removeDuplicates(num) {
  let i = 0;
  while (i < nums.length) {
    if (nums[i] === nums[i + 1]) {
      nums.splice(i, 1);
    } else {
      i++;
    }
  }
  return nums.length;
}
```
