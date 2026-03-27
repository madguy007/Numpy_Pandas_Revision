# NumPy np.diff() — Quick Notes

---

## Key Difference
Computes difference between consecutive elements → (next - current)

---

## Example
arr = [50, 30, 40, 80, 40]  
np.diff(arr)

---

## Output
[-20, 10, 40, -40]

---

## Type of Output
NumPy array (length = n-1)

---

## Explanation
Each value is calculated as: arr[i+1] - arr[i]  
So:  
50→30 = -20  
30→40 = +10  
40→80 = +40  
80→40 = -40  

---

## Key Intuition
“Compare next value with current value”

---

## When to Use
- Trend detection (increase/decrease)  
- Time-series change analysis  
- Finding gradients or step changes  
- Preprocessing before ML models  

---

## Important Notes
- Output size is always one less than input  
- Indices refer to transition (i → i+1), not actual element index  
- Works along axis in multi-dimensional arrays  
- Higher order diff: np.diff(arr, n=2) → diff of diff  
- For 2D: axis=0 → row-wise, axis=1 → column-wise  

---

## One-line Summary
np.diff = “next element minus current element”
