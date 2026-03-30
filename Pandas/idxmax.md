# Pandas `idxmax()` — Quick Revision

## What is idxmax()?

`idxmax()` returns the **index label where the maximum value occurs**.

---

## Key Idea

* `max()` → gives the maximum value
* `idxmax()` → gives **where (Index) that value occurs**

---

## Works on Series

Example:
import pandas as pd

s = pd.Series([10, 50, 30], index=['A', 'B', 'C'])

print(s.idxmax())

Output:
B

Explanation:
50 is the maximum value → its label is 'B'

---

## Works on DataFrame
```
Example:
import pandas as pd

df = pd.DataFrame({
'A': [1, 5, 3],
'B': [4, 2, 6]
})

print(df.idxmax())

Output:
A    1
B    2
```
Explanation:
Column A → max at index 1
Column B → max at index 2

---

## Using axis

df.idxmax(axis=0)
→ default → gives index of max value for each column

df.idxmax(axis=1)
→ gives column name where max occurs in each row
```
Example:
print(df.idxmax(axis=1))

Output:
0    B
1    A
2    B
```
---

## Important Notes

* Returns **label**, not position
* If multiple max values → returns **first occurrence**

---

## idxmax vs argmax

* `np.argmax()` → returns position (0,1,2...)
* `idxmax()` → returns label (A,B,C...)

---

## One-Line Summary

`idxmax()` = "give me the label where maximum value occurs"
