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
```
## 🔹 Rolling Average (np.convolve)

**Works by (step → step):**
- Create averaging filter
- Slide it over array
- Multiply + sum at each step

---

## 🔹 Example

```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])
window = 3

result = np.convolve(arr, np.ones(window)/window, mode='valid')
print(result)  # [2. 3. 4.]
```
🔹 Explanation
np.ones(window)/window → [1,1,1]/3 = [0.33, 0.33, 0.33]
Convolution → sliding window → multiply + sum
mode='valid' → only full windows (no padding)

🔹 Modes
'valid' → no padding (smaller output)
'same' → same size output
'full' → includes padding (larger output)
