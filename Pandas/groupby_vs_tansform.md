# Pandas `groupby().agg()` vs `groupby().transform()` — Quick Revision

## 🔹 Core Difference
- **agg() → reduces data (one row per group)**
- **transform() → preserves original shape (same rows as input)**

---

## 🔹 What Happens Internally

### groupby().agg()
- Splits data into groups based on key(s)
- Applies aggregation (min, max, sum, etc.)
- Combines results into a **smaller output**
- Output index = **group keys**

```python
df.groupby('player_id')['event_date'].agg('min')
````

Output:

```
player_id
1   2016-03-01
2   2017-06-25
3   2016-03-02
```

---

### groupby().transform()

* Splits data into groups
* Applies function to each group
* **Broadcasts result back to each row in that group**
* Output index = **original DataFrame index**

```python
df.groupby('player_id')['event_date'].transform('min')
```

Output:

```
0   2016-03-01
1   2016-03-01
2   2017-06-25
3   2016-03-02
4   2016-03-02
```

---

## 🔹 Real Difference (Side-by-Side)

| Feature        | `agg()`     | `transform()`                |
| -------------- | ----------- | ---------------------------- |
| Output size    | Reduced     | Same as input                |
| Index          | Group keys  | Original index               |
| Operation type | Aggregation | Element-wise group operation |
| Shape change   | Yes         | No                           |

---

## 🔹 When to Use What

### ✅ Use `agg()` (Aggregation)

* When you need **summary results**
* Reporting, metrics, KPIs

```python
df.groupby('player_id')['games_played'].agg('sum')
```

---

### ✅ Use `transform()` (Feature Engineering)

* When you need **group info per row**
* Creating new columns

```python
df['first_login'] = df.groupby('player_id')['event_date'].transform('min')
```

---

## 🔹 Mental Model

* **agg() → "collapse groups"**
* **transform() → "compute per group, return per row"**

```
```
