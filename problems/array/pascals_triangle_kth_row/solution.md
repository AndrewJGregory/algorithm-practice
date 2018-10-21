# PASCALS TRIANGLE KTH ROW

```rb
def get_row(row_index)
    current_row = [1]
    i = 1
    while i <= row_index
        next_row = [1]
        j = 1
        while j < current_row.length
            next_row << current_row[j-1] + current_row[j]
            j += 1
        end
        next_row << 1
        current_row = next_row
        i += 1
    end
    current_row
end
```

```js
var getRow = function(rowIndex) {
  let currentRow = [1];
  for (let i = 0; i < rowIndex; i++) {
    let nextRow = [1];
    for (let j = 1; j < currentRow.length; j++) {
      nextRow.push(currentRow[j - 1] + currentRow[j]);
    }
    nextRow.push(1);
    currentRow = nextRow.slice();
  }
  return currentRow;
};
```
