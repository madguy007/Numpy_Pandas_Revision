### Axis (axis=0 vs axis=1 in NumPy & Pandas)
WHAT IS IT

- Axis defines the direction of an operation.
- It tells which dimension gets reduced or removed during computation.

### SYNTAX / CORE IDEA

- axis=0 → remove rows (operate column-wise)
- axis=1 → remove columns (operate row-wise)

```
EXAMPLE
import numpy as np
import pandas as pd

arr = np.array([[1, 2],
                [3, 4]])

print(np.sum(arr, axis=0))  # column-wise
print(np.sum(arr, axis=1))  # row-wise

df = pd.DataFrame({
    'A': [1, None],
    'B': [3, 4]
})

print(df.dropna(axis=0))  # drop rows with NaN
print(df.dropna(axis=1))  # drop columns with NaN

Output:
[4 6]
[3 7]
A B
0 1.0 3
B
0 3
1 4
```
### CONDITIONS / RULES
- axis=0 → rows are removed or reduced
- axis=1 → columns are removed or reduced
- NumPy: axis defines direction of computation
- Pandas: axis defines what gets dropped or aggregated
- axis works the same conceptually across libraries
- Always think: axis = dimension being collapsed
