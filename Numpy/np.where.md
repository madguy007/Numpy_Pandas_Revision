# NumPy np.where() — Quick Revision

## What is np.where()?

np.where() is used for conditional selection in NumPy arrays.

---

## Syntax

np.where(condition, x, y)

* condition → boolean condition
* x → value if condition is True
* y → value if condition is False

---

## Case 1: Condition Only (Find Indices)

Returns indices where condition is True.

Example:
import numpy as np

arr = np.array([1, 5, 2, 8])

result = np.where(arr > 3)
print(result)

Output:
(array([1, 3]),)

---

## Case 2: Vectorized If-Else (Most Important)

Example:
import numpy as np

arr = np.array([1, 5, 2, 8])

result = np.where(arr > 3, 100, 0)
print(result)

Output:
[  0 100   0 100]

---

## Case 3: 2D Array Example

Example:
import numpy as np

arr = np.array([[1, 6],
[3, 8]])

result = np.where(arr > 5, 1, 0)
print(result)

Output:
[[0 1]
[0 1]]

---

## Key Intuition

* Works like vectorized if-else
* Applies condition to entire array at once
* No loops required

---

## One-Line Summary

np.where() = Apply condition → pick values accordingly (if-else for arrays)
