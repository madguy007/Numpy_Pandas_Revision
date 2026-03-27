# Pandas `nunique()` vs `value_counts()` — Quick Revision

## Key Difference

* `nunique()` → number of unique values
* `value_counts()` → frequency of each value

---

## Example

import pandas as pd

s = pd.Series([1, 2, 2, 3, 3, 3])

---

## nunique()

s.nunique()

Output:
3

Type of Output:

* Returns a **single integer (int)**
* NOT a set ❌

Explanation:
Unique values = {1, 2, 3} → total = 3

---

## value_counts()

s.value_counts()

Output:
3    3
2    2
1    1

Type of Output:

* Returns a **Series**
* Index → unique values
* Values → their frequency

Explanation:
3 appears 3 times
2 appears 2 times
1 appears 1 time

---

## Key Intuition

* nunique() → “how many different values?”
* value_counts() → “how many times each value?”

---

## When to Use

* Count distinct categories → nunique()
* Get frequency distribution → value_counts()

---

## Important Note

s.value_counts().nunique()

👉 counts how many UNIQUE frequencies exist (not values)

Example:
values frequency = [3, 2, 1] → unique = 3

---

## One-Line Summary

nunique() = integer (count of unique values)
value_counts() = Series (value → frequency mapping)
