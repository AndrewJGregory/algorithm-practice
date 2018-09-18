# SQUARE ROOT

```rb
def my_sqrt(x)
  return x if x < 2
  left = 0
  right = (x/2.0).floor
  while left <= right
    mid = (left + right) / 2
    after = mid + 1
    if (mid * mid <= x) && (after * after > x)
      return mid
    elsif (mid * mid > x)
      right = mid - 1
    else
      left = mid + 1
    end
  end
end
```

```js
var mySqrt = function(x) {
  if (x < 2) return x;
  let left = 0;
  let right = Math.floor(x / 2);
  while (left <= right) {
    let mid = Math.floor((left + right) / 2);
    let next = mid + 1;
    if (mid * mid <= x && next * next > x) {
      return mid;
    } else if (mid * mid > x) {
      right = mid - 1;
    } else {
      left = mid + 1;
    }
  }
};
```
