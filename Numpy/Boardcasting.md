## 🔹 Broadcasting (NumPy)

**Works when (right → left):**
- Dimensions are **same**, OR
- One of them is **1**
- Missing dimensions are treated as **1**

---

## 🔹 Example

```python
import numpy as np

a = np.array([[1], [2], [3]])   # shape (3,1)
b = np.array([10, 20, 30, 40])  # shape (4,) → treated as (1,4)

print(a + b)  # shape (3,4)

[[11 21 31 41]
 [12 22 32 42]
 [13 23 33 43]]
