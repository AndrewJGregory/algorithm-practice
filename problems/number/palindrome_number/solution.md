# PALINDROME NUMBER

```rb
def number_is_palindrome?(num)
  return false if num < 0 || num % 10 == 0 && num != 0

  revNum = 0
  while num > revNum
    revNum = (revNum * 10) + (num % 10)
    num /= 10
  end

  return revNum === num || revNum/10 === num
end
```

```js
function isNumPalindrome(num) {
  if (num < 0 || num % 10 === 0 && num !== 0) {
    return false;
  }

  let revNum = 0;
  while (num > revNum) {
    revNum = (revNum * 10) + (num % 10);
    num = Math.floor(num/10);
  }


  return revNum === num || Math.floor(revNum/10) === num; //mod the revNum due to while loop logic
}
```
