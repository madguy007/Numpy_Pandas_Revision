# ⚡  Vectorization (CORE CONCEPT) + question

## ✅ Definition

```text
Apply operation on entire column/array at once (no loops)
```

---

## ❌ Loop (bad)

```python
for i in range(len(df)):
    df.loc[i, 'col'] *= 2
```

---

## ✅ Vectorized (good)

```python
df['col'] = df['col'] * 2
```

---

## 🧠 Key Idea

```text
Think in columns, not rows
```

---

# 🔁 5. Your Swap Problem (Vectorized)

## 🎯 Goal

```text
[A, B, C, D] → [B, A, D, C]
```

---

## ✅ Solution

```python
seat_df['student'] = seat_df['student'].values.reshape(-1, 2)[:, ::-1].flatten()
```

---

## 🔍 Step Breakdown

```text
1. values       → convert to NumPy
2. reshape(-1,2)→ group into pairs
3. [:, ::-1]    → reverse each pair
4. flatten()    → back to 1D
```

---

## 🧠 `-1` Meaning

```text
-1 = auto-calculate dimension
```

Example:

```python
.reshape(-1, 2)
```

```text
4 elements → 2 columns → 2 rows automatically
```

---

# ⚠️ 6. Why Your Loop Swap Failed

```python
seat_df.loc[i,'student'], seat_df.loc[i+1,'student'] = ...
```

## ❌ Problem

* Pandas assignment is **not atomic**
* Values may overwrite incorrectly

---

## ✅ Safe Fix

```python
temp = seat_df.loc[i, 'student']
seat_df.loc[i, 'student'] = seat_df.loc[i+1, 'student']
seat_df.loc[i+1, 'student'] = temp
```
