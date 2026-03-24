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

## 🔹 Rolling Average (np.convolve)

**Idea:**
- Use convolution to compute moving average

---

## 🔹 Example

```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])
window = 3

result = np.convolve(arr, np.ones(window)/window, mode='valid')
print(result)  # [2. 3. 4.]
🔹 Key Points
np.ones(window)/window → averaging filter (equal weights)
np.convolve(arr, filter) → sliding window (multiply + sum)
mode='valid' → only full windows (no padding)
🔹 Modes
'valid' → smaller output (no padding)
'same' → same size as input
'full' → larger output (with padding)
