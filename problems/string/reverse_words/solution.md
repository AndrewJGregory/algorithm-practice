# REVERSE WORDS

```rb
def reverse(sentence, start, end_idx)
  while start < end_idx do
    hold = sentence[start]
    sentence[start] = sentence[end_idx]
    sentence[end_idx] = hold

    start += 1
    end_idx -= 1
  end
end

def reverse_words(sentence)
  reverse(sentence, 0, sentence.length - 1)
  current_start_idx = 0

  sentence.each_with_index do |el, i|
    if el == ' ' || el == sentence.length - 1
      reverse(sentence, current_start_idx, i - 1)
      current_start_idx = i + 1
    end
  end

  sentence
end
```

```js
// the sentence should be given as an array
function reverse(sentence, start, end) {
  while (start < end) {
    const hold = sentence[start];
    sentence[start] = sentence[end];
    sentence[end] = hold;

    start++; 
    end--;
  }
}

function reverseWords(sentence) {
  reverse(sentence, 0, sentence.length - 1);
  let currentWordStartIdx = 0;
  for (let i = 0; i <= sentence.length; i++) {
    if (sentence[i] === ' ' || i === sentence.length) {
      reverse(sentence, currentWordStartIdx, i - 1);
      currentWordStartIdx = i + 1;
    }
  }

  return sentence;
}
```
