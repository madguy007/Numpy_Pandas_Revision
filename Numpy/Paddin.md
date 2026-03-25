===CONCEPT===
NumPy Padding (np.pad)

===WHAT IS IT===
`np.pad()` is used to add extra values (padding) around an array.
It helps in resizing arrays or handling edge cases in operations like convolution.
You can control how padding values are filled.

===SYNTAX / CORE IDEA===
np.pad(array, pad_width, mode='constant')

===EXAMPLE===
```python
import numpy as np

arr = np.array([1, 2, 3])

result = np.pad(arr, pad_width=2, mode='constant')
print(result)

Output:

[0 0 1 2 3 0 0]

===CONDITIONS / RULES===

pad_width defines number of values added on each side
Default mode is 'constant' (fills with 0)
Other modes: 'edge', 'reflect', 'wrap'
Works for both 1D and multi-dimensional arrays
Padding shape depends on input dimensions
