# GUESS NUMBER

```py
class Solution(object):
    def guessNumber(self, n):
      left = 0
      right = n
      while left <= right:
        num = (left + right)/2
        result = guess(num)
        if result == 0:
          return num
        elif result == 1:
          left = num + 1
        else:
          right = num - 1
```
