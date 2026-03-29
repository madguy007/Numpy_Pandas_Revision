
# 🧠 NumPy Revision Sheet: `np.any()`, `np.all()`, `np.array_equal()`

---

## 🔹 1. `np.any()`

### Explanation
Checks if **at least one element** in the array satisfies a condition (True).

### Syntax
```python
np.any(array, axis=None)
````

### Example

```python
import numpy as np

arr = np.array([0, 0, 1, 0])

np.any(arr)            # True
np.any(arr > 2)        # False
```

### Key Points

* Returns **True if ANY value is True / non-zero**
* Commonly used for **existence checks**
* Works with conditions (`arr > value`)
* Supports `axis` for row/column-wise checks

---

## 🔹 2. `np.all()`

### Explanation

Checks if **all elements** in the array satisfy a condition (True).

### Syntax

```python
np.all(array, axis=None)
```

### Example

```python
import numpy as np

arr = np.array([1, 2, 3])

np.all(arr)            # True
np.all(arr > 1)        # False
```

### Key Points

* Returns **True only if ALL values are True / non-zero**
* Useful for **validation checks**
* Works with conditions (`arr > value`)
* Supports `axis` for row/column-wise validation

---

## 🔹 3. `np.array_equal()`

### Explanation

Checks if **two arrays are exactly equal** (same shape and values).

### Syntax

```python
np.array_equal(arr1, arr2)
```

### Example

```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([1, 2, 3])

np.array_equal(a, b)   # True
```

### Key Points

* Returns **True only if shape + elements match**
* Better than `a == b` (which is element-wise)
* Handles full-array comparison in one step
* Does NOT treat `NaN` values as equal

---

# 🔥 Most Important Interview Concepts

* `np.any()` → check if **any condition is satisfied**
* `np.all()` → check if **all conditions are satisfied**
* `np.array_equal()` → check **exact equality of arrays**
* Avoid using `a == b` alone → it gives **element-wise output**
* Use `np.all(a == b)` if needed as an alternative

---

# ⚡ Mental Model / When to Use What

* Use `np.any()` → when looking for **existence of a condition**
* Use `np.all()` → when validating **entire dataset condition**
* Use `np.array_equal()` → when checking **full equality between arrays**
* Use `axis` → when applying checks **row-wise or column-wise**

---

```
```
