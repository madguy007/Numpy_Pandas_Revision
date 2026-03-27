# Pandas `.loc[]` — Quick Revision (Series vs DataFrame Output)

## Key Idea

`.loc[]` does NOT change type by itself.
👉 The **selection you make decides the output**.

---

## Output Rules

| Selection               | Output                |
| ----------------------- | --------------------- |
| 1 row + 1 column        | scalar (single value) |
| 1 row                   | Series                |
| 1 column                | Series                |
| multiple rows + columns | DataFrame             |

---

## Examples

### 1. Single column → Series

import pandas as pd

df.loc[:, 'age']

---

### 2. Single row → Series

df.loc[0]

---

### 3. Single value → scalar

df.loc[0, 'age']

---

### 4. Rows + multiple columns → DataFrame

df.loc[df['age'] > 25, ['name', 'age']]

---

## Important Trick (VERY USEFUL)

👉 Use **double brackets** to force DataFrame output

df.loc[:, ['age']]        # DataFrame (not Series)
df.loc[0:2, ['age']]      # DataFrame

---

## Common Mistake

df.loc[:, 'col']     # Series ❌ (if you expected DataFrame)

df.loc[:, ['col']]   # DataFrame ✅

---

## With Filtering

df.loc[df['col'] > 10, ['A','B']]

👉 Filter rows + select columns → DataFrame

---

## Series vs DataFrame Rule

* Series → no column selection inside
* DataFrame → column selection required

---

## One-Line Summary

`.loc[]` output depends on selection:
👉 single axis → Series
👉 multiple axes → DataFrame
