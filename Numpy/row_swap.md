## NumPy Row Swap

### WHAT IS IT
Row swapping means exchanging positions of two rows in a 2D array.
It is commonly used in matrix operations and algorithms like Gaussian elimination.
NumPy allows direct row swapping using indexing.

### SYNTAX / CORE IDEA
`arr[[i, j]] = arr[[j, i]]`

### EXAMPLE
```python
import numpy as np

arr = np.array([[1, 2, 3],
                [4, 5, 6],
                [7, 8, 9]])

arr[[0, 2]] = arr[[2, 0]]

print(arr)

Output:
[[7 8 9]
[4 5 6]
[1 2 3]]

```

CONDITIONS / RULES
Works only for 2D (or higher) arrays
Uses advanced indexing
Swaps rows in-place
Indices must be valid
Can swap multiple rows at once
