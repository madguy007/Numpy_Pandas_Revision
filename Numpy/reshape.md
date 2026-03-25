## NumPy Reshape (np.reshape)

### WHAT IS IT
Reshape changes the shape (dimensions) of an array without changing its data.
It helps convert a 1D array into 2D/3D or rearrange existing dimensions.
Useful for preparing data for models and matrix operations.

### SYNTAX / CORE IDEA
`arr.reshape(new_shape)` or `np.reshape(arr, new_shape)`

### EXAMPLE
```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6])

result = arr.reshape(2, 3)

print(result)

Output:
[[1 2 3]
[4 5 6]]

CONDITIONS / RULES
Total elements must remain the same (2×3 = 6)
Can use -1 to automatically infer one dimension
Returns a new view (no data copy if possible)
Works for converting between 1D, 2D, and higher dimensions
Invalid shapes will raise an error
