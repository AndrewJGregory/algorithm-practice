# PASCALS TRIANGLE

```rb
def generate(num_rows)
    return [] if (num_rows <= 0)
    rows = [[1]]
    i = 0
    num_rows -= 1
    while i < num_rows
        last_row = rows.last
        j = 1
        new_row = [1]
        while j < last_row.length
            first_num = last_row[j-1]
            second_num = last_row[j]
            new_row << first_num + second_num
            j += 1
        end
        new_row << 1
        rows << new_row
        i += 1
    end
    rows
end
```

```js
var generate = function(numRows) {
  if (numRows <= 0) return [];
  const rows = [[1]];
  numRows -= 1;
  for (let i = 0; i < numRows; i++) {
    const lastRow = rows[rows.length - 1];
    let newRow = [];
    for (let j = 0; j <= lastRow.length; j++) {
      const firstNum = lastRow[j - 1] === undefined ? 0 : lastRow[j - 1];
      const secondNum = lastRow[j] === undefined ? 0 : lastRow[j];
      newRow.push(firstNum + secondNum);
    }
    rows.push(newRow);
  }
  return rows;
};
```
