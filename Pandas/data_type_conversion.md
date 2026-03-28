# Conversions

---

# 📌 1. Core Mental Model

```text
DataFrame = 2D table (rows + columns)
Series    = 1D column
NumPy     = raw array (no labels, fast)
```

---

# 🔁 2. Conversions (VERY IMPORTANT)

## ✅ DataFrame → Series

```python
s = df['col']        # column
s = df.loc[0]        # row
```

---

## ✅ Series → DataFrame

```python
df = s.to_frame()
df = s.to_frame(name='col_name')
```

---

## ✅ DataFrame → NumPy

```python
arr = df.to_numpy()   # preferred
arr = df.values       # also works
```

---

## ✅ Series → NumPy

```python
arr = s.to_numpy()
```

---

## ✅ NumPy → DataFrame

```python
df = pd.DataFrame(arr, columns=['A', 'B'])
```

---

## ✅ NumPy → Series

```python
s = pd.Series(arr)
```

---

# 🔥 3. When to Use What

| Use Case                   | Tool   |
| -------------------------- | ------ |
| Labels, filtering, groupby | Pandas |
| Fast math, reshape         | NumPy  |

---

## 🧠 Workflow

```text
Pandas → NumPy → Operation → Pandas
```




# ⚡ Ultimate One-Line Takeaway

👉 **“Transform the whole column, not each row”**

---
