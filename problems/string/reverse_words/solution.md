# REVERSE WORDS IN A STRING

```js
var reverseWords = function(str) {
  str = trimSpaces(str); // or str.trim()
  str = reduceMultipleSpaces(str);
  let result = "";
  let word = "";
  for (let i = str.length - 1; i >= 0; i--) {
    const ch = str[i];
    if (ch !== " ") {
      word = ch + word;
    } else {
      result += word + " ";
      word = "";
    }
  }
  result += word;
  return result;
};

var trimSpaces = function(str) {
  let newStr = "";
  let startIdx = 0;
  for (let i = 0; i < str.length; i++) {
    const ch = str[i];
    if (ch !== " ") {
      startIdx = i;
      break;
    }
  }

  if (startIdx === 0 && str[0] === " ") return "";

  let endIdx = str.length - 1;
  for (let i = str.length - 1; i >= 0; i--) {
    const ch = str[i];
    if (ch !== " ") {
      endIdx = i;
      break;
    }
  }
  return str.slice(startIdx, endIdx + 1);
};

var reduceMultipleSpaces = function(str) {
  let newStr = "";
  for (let i = 0; i < str.length; i++) {
    const ch = str[i];
    if (ch !== " ") {
      newStr += ch;
    } else if (ch === " ") {
      if (newStr[newStr.length - 1] !== " ") newStr += ch;
    }
  }
  return newStr;
};
```
