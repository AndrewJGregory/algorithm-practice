# REVERSE STRING

```rb
def reverse_string(str)
  str.reverse
end

### this problem not as exciting at all in ruby. Ruby has a efficient string reverse method
```

```js
function longestCommonPrefix(str) {
  let rStr = '';
  for (let i = str.length - 1; i >= 0; i--) {
    rStr += str[i];
  }
  return rStr;
}
```
