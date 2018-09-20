# VALID PERFECT SQUARE

```rb
def is_perfect_square(num)
  left = 0
  right = (num/2.0).ceil
  while left <= right
    mid = (left + right)/2
    square = mid * mid
    if square == num
      return true
    elsif square < num
      left = mid + 1
    else
      right = mid - 1;
    end
  end
  false
end
```

```js
var isPerfectSquare = function(num) {
  let left = 0;
  let right = Math.ceil(num / 2);
  while (left <= right) {
    let mid = Math.floor((left + right) / 2);
    let square = mid * mid;
    if (square === num) {
      return true;
    } else if (square < num) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }
  return false;
};
```
