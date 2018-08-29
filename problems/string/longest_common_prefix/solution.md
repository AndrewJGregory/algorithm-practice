# LONGEST COMMON PREFIX

```rb
def longest_common_prefix(strs)
  return "" if strs.empty?
  first_word = strs.first
  i = 0
  while i < first_word.length
    if strs.all? { |str| str[0..i] == first_word[0..i] }
      i += 1
    else
      break
    end
  end
  return first_word[0...i]
end
```

```js
function longestCommonPrefix(strs) {
  if (strs.length === 0) return "";
  const firstWord = strs[0];
  let i = 0;
  while (i < firstWord.length) {
    if (strs.every(str => str.slice(0, i + 1) === firstWord.slice(0, i + 1))) {
      i += 1;
    } else {
      break;
    }
  }
  return firstWord.slice(0, i);
}
```
