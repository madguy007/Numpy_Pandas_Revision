## NumPy unique(), max() and argmax() (for Mode)

### WHAT IS IT
`np.unique()` finds unique values and their frequencies.  
`counts.max()` gives the highest frequency.  
`np.argmax(counts)` gives the index of that highest frequency.  
Together, they help identify the mode of an array.

### SYNTAX / CORE IDEA
`values, counts = np.unique(arr, return_counts=True)`  
`counts.max()` → max frequency  
`np.argmax(counts)` → index of max frequency  

### EXAMPLE
```python
import numpy as np

arr = np.array([1, 2, 2, 3, 3, 3])

values, counts = np.unique(arr, return_counts=True)

mode = values[np.argmax(counts)]
max_count = counts.max()
modes = values[counts == counts.max()]

print(values, counts, mode, max_count, modes)

Output:
[1 2 3] [1 2 3] 3 3 [3]
```

CONDITIONS / RULES
- np.unique() returns sorted unique values
- return_counts=True gives frequency of each value
- counts.max() returns highest frequency
- np.argmax() returns index of highest frequency
- Boolean mask counts == counts.max() → [False False True]
- Mask selects matching values → values[...]
- For multiple modes, returns all matching values
- Works best for 1D arrays (flatten if needed)
