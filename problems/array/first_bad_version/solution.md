# FIRST BAD VERSION

```rb
def first_bad_version(n)
    left = 1
    while left < n
        mid = (left + n)/2
        is_mid_bad = is_bad_version(mid)
        is_after_bad = is_bad_version(mid + 1)
        if !is_mid_bad && is_after_bad
            return mid + 1
        elsif !is_mid_bad && !is_after_bad
            left = mid + 1
        else
            n = mid
        end
    end
    return left
end
```

```js
var solution = function(isBadVersion) {
  return function(n) {
    let left = 1;
    while (left < n) {
      let mid = Math.floor((left + n) / 2);
      let isMidGood = !isBadVersion(mid);
      let isNextBad = isBadVersion(mid + 1);
      if (isMidGood && isNextBad) {
        return mid + 1;
      } else if (!isMidGood && isNextBad) {
        n = mid;
      } else {
        left = mid + 1;
      }
    }
    return left;
  };
};
```
