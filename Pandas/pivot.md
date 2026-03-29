
# 📊 Pandas Pivot — Ultra Short Revision

## 🔹 pivot()
- Reshape data (no aggregation)
- ❌ Fails on duplicates
```python
df.pivot(index='A', columns='B', values='C')
````

## 🔹 pivot_table()

* Reshape + aggregation
* ✅ Handles duplicates

```python
df.pivot_table(index='A', columns='B', values='C', aggfunc='sum')
```

## 🔹 Common aggfunc

* `'sum'`, `'mean'`, `'count'`, `'size'`

## 🔹 Fill missing

```python
fill_value=0
```

## 🔹 Intersection Pattern

```python
p = df.pivot_table(index='user', columns='platform', aggfunc='size', fill_value=0)
p[(p['web'] > 0) & (p['app'] > 0)]
```

## 🔹 pivot vs pivot_table

* pivot → clean data
* pivot_table → real-world data

## 🔹 Alternative

```python
df.groupby(['A','B']).size().unstack(fill_value=0)
```

## 🧠 TL;DR

pivot = reshape
pivot_table = reshape + aggregate

```
```
