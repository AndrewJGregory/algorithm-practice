# REVERSE INTEGER

```rb
def reverse_int(x)
  num = x.abs
  revNum = 0

  while num > 0
    revNum = (revNum * 10) + (num % 10)
    num /= 10
  end

  return 0 if revNum >= 2 ** 31 - 1 || -revNum <= - 2**31

  x > 0 ? revNum : -revNum
end

# reversing the integer as a string runs faster in ruby
```

```js
function reverseInt(x) {
  let num = Math.abs(x);
  let revNum = 0;

  while (num > 0) {
      revNum = (revNum * 10) + (num % 10);
      num = Math.floor(num/10);
  }

  if (revNum >= Math.pow(2,31) - 1 || -revNum <= -Math.pow(2,31)) return 0;
  return x > 0 ? revNum : -revNum
}
```
