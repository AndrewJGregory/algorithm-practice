# Plus One

```rb
def plus_one(digits)
    if digits.last != 9
        digits[-1] += 1
        return digits
    end

    idx = digits.length - 1
    last_digit = digits[idx]
    while last_digit == 9
        idx -= 1
        last_digit = digits[idx]
        break if last_digit.nil?
    end

    if last_digit.nil?
        original_size = digits.length
        digits = [1]
        original_size.times { digits << 0 }
    else
        digits[idx] += 1
        idx += 1
        while idx < digits.length
            digits[idx] = 0
            idx += 1
        end
    end
    return digits
end
```

```js
var plusOne = function(digits) {
  let lastDigit = digits[lastIdx];
  if (lastDigit + 1 !== 10) {
    digits[lastIdx]++;
    return digits;
  }

  while (lastDigit + 1 === 10) {
    lastIdx--;
    if (lastIdx === undefined) break;
    lastDigit = digits[lastIdx];
  }

  if (lastDigit === undefined) {
    // all 9s
    digits = [1].concat(new Array(digits.length).fill(0));
  } else {
    // some 9s
    digits[lastIdx]++;
    for (let i = lastIdx + 1; i < digits.length; i++) digits[i] = 0;
  }
  return digits;
};
```
