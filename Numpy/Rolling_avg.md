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
🔹 Explanation

np.ones(window)/window → [1,1,1]/3 = [0.33, 0.33, 0.33]
Convolution → sliding window → multiply + sum
mode='valid' → only full windows (no padding)
🔹 Modes

'valid' → no padding (smaller output)
'same' → same size output
'full' → includes padding (larger output)
