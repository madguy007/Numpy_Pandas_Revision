## NumPy Padding (np.pad)

### WHAT IS IT
np.pad() adds extra values (padding) around an array.  
Used to resize arrays or handle edge cases like convolution.  
You can control how padding values are filled.

### SYNTAX / CORE IDEA
`np.pad(array, pad_width, mode='constant')`

### EXAMPLE
```python
import numpy as np

arr = np.array([1, 2, 3])
result = np.pad(arr, pad_width=2, mode='constant')

print(result)

Output:

[0 0 1 2 3 0 0]
CONDITIONS / RULES
pad_width → number of values added on each side
default mode = 'constant' (fills with 0)
other modes: 'edge', 'reflect', 'wrap'
works for 1D and multi-dimensional arrays
padding depends on array dimensions
