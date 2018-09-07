# ROTATE IMAGE

```rb
def rotate(matrix)
  transpose(matrix)
  matrix.map!(&:reverse)
  nil
end

def transpose(matrix)
  i = 0
  while i < matrix.length
    j = i
    while j < matrix.length
      matrix[i][j], matrix[j][i] = matrix[j][i], matrix[i][j]
      j += 1
    end
    i += 1
  end
end
```

```js
var rotate = function(matrix) {
  transpose(matrix);
  matrix.forEach(reverse);
};

const transpose = function(matrix) {
  for (let i = 0; i < matrix.length; i++) {
    for (let j = i; j < matrix.length; j++) {
      let temp = matrix[i][j];
      matrix[i][j] = matrix[j][i];
      matrix[j][i] = temp;
    }
  }
};

const reverse = function(row) {
  for (let i = 0; i < row.length / 2; i++) {
    let temp = row[i];
    row[i] = row[row.length - i - 1];
    row[row.length - i - 1] = temp;
  }
};
```
