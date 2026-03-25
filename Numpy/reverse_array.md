## NumPy Reverse 2D Array (Row-wise and Column-wise)

### WHAT IS IT
Reversing a 2D array means flipping its elements either across rows or columns.
Row-wise reversal flips left ↔ right, while column-wise reversal flips top ↔ bottom.
This is commonly used in matrix transformations and image processing.

### SYNTAX / CORE IDEA
`arr[:, ::-1]` → reverse columns (row-wise)  
`arr[::-1, :]` → reverse rows (column-wise)

### EXAMPLE
```python
import numpy as np

arr = np.array([[1, 2, 3],
                [4, 5, 6]])

result = arr[::-1, ::-1]

print(result)

Output:
[[6 5 4]
[3 2 1]]

CONDITIONS / RULES
[::-1] reverses along a specific axis
arr[:, ::-1] flips elements in each row
arr[::-1, :] flips entire row order
arr[::-1, ::-1] reverses both rows and columns
Works for any 2D NumPy array
Does not modify original array (returns a view)
