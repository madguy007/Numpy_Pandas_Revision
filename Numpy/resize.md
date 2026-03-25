## NumPy Resize (np.resize)

### WHAT IS IT
np.resize() changes the size of an array to a new shape.
If the new size is larger, it repeats the original data.
If smaller, it truncates the extra elements.

### SYNTAX / CORE IDEA
`np.resize(arr, new_shape)`

### EXAMPLE
```python
import numpy as np

arr = np.array([1, 2, 3, 4])

result = np.resize(arr, (2, 3))

print(result)

Output:
[[1 2 3]
[4 1 2]]

CONDITIONS / RULES
Repeats elements if new size > original size
Cuts off elements if new size < original size
Returns a new array (not in-place)
Works for any shape conversion
Does not preserve row/column structure (just repeats sequentially)
