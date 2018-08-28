# LONGEST COMMON PREFIX

```rb
def longest_common_prefix(strs)
  return "" if strs.empty?
  first_word = strs.first
  result = ""
  i = 0
  while i < first_word.length
    prefix = first_word[0..i]
    if strs.all? { |str| str[0..i] == prefix}
      result = prefix
    else
      return result
    end
    i += 1
  end
  return result
end
```

```js
function longestCommonPrefix(strs) {
  if (strs.length === 0) return "";
  const firstWord = strs[0];
  let result = "";
  let prefix;
  for (let i = 0; i < firstWord.length; i++) {
    prefix = firstWord.slice(0, i + 1);
    if (strs.every(str => str.slice(0, i + 1) === prefix)) {
      result = prefix;
    } else {
      return result;
    }
  }
  return result;
}
```
