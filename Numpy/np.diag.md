## NumPy: 1D Array → Diagonal Matrix

### Concept
- `np.diag(arr)` → converts **1D array → diagonal matrix**
- `np.diag(matrix)` → extracts **diagonal → 1D array**

### Syntax
```python
np.diag(v, k=0)
v → input array
k=0 → main diagonal
k>0 → above diagonal
k<0 → below diagonal
Example
```
import numpy as np

arr = np.array([1, 2, 3])

diag_matrix = np.diag(arr)
print(diag_matrix)
Output
[[1 0 0]
 [0 2 0]
 [0 0 3]]
 ```
