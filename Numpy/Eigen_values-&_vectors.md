## NumPy Eigenvalues and Eigenvectors (np.linalg.eig)

### WHAT IS IT
Eigenvalues and eigenvectors describe how a matrix transforms vectors.
Eigenvectors remain in the same direction after transformation, scaled by eigenvalues.
Used in PCA, linear algebra, and ML.

### SYNTAX / CORE IDEA
`values, vectors = np.linalg.eig(matrix)`

### EXAMPLE
```python
import numpy as np

arr = np.array([[2, 0],
                [0, 3]])

values, vectors = np.linalg.eig(arr)

print(values)
print(vectors)

Output:
[2. 3.]
[[1. 0.]
[0. 1.]]
```
#CONDITIONS / RULES
- Works only for square matrices
- Returns eigenvalues and corresponding eigenvectors
- Each column in vectors is an eigenvector
- Order of eigenvalues may vary
- Can return complex numbers for some matrices
- Use for linear transformations and dimensionality reduction
