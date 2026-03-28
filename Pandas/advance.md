# 📊 Pandas Complete Revision Sheet

> Source: Colab Notes :contentReference[oaicite:0]{index=0}

---

# 1️⃣ Setup & Quick EDA

## 📌 Basic Inspection
Used to quickly understand dataset structure, types, and distribution.

```python
df.head()
df.info()
df.describe(include="all")
df.sample(5)
```

**Key Points:**
- `head()` → first rows
- `info()` → dtypes + nulls
- `describe()` → stats
- `sample()` → random rows

---

# 2️⃣ Core Manipulation

## 📌 query() — SQL-style filtering
```python
df.query("day == 'Sun' and total_bill > 20")
```
- Cleaner than boolean masking
- Similar to SQL WHERE

---

## 📌 isin() + NOT (~)
```python
df[df["day"].isin(["Sat", "Sun"])]
df[~df["smoker"].isin(["Yes"])]
```
- Filter multiple values
- `~` = NOT

---

## 📌 assign() — create/modify columns
```python
df.assign(tip_pct=lambda x: x.tip / x.total_bill * 100)
```
- Chain-friendly
- Avoids temporary variables

---

## 📌 rename() & drop()
```python
df.rename(columns={"total_bill": "bill"})
df.drop(columns=["size"])
```
- Rename columns
- Remove unwanted columns

---

## 📌 nlargest() / nsmallest()
```python
df.nlargest(5, "tip_pct")
```
- Faster than sorting
- Used for Top-N queries

---

# 3️⃣ Aggregations & Group Operations

## 📌 groupby() + agg()
```python
df.groupby(["day", "time"]).agg({
    "total_bill": "mean",
    "tip": "mean"
})
```
- SQL GROUP BY equivalent
- Multiple aggregations

---

## 📌 transform()
```python
df["centered"] = df["tip"] - df.groupby("day")["tip"].transform("mean")
```
- Output same size as original
- Used for feature engineering

---

## 📌 filter()
```python
df.groupby("day").filter(lambda g: g["tip"].mean() > 3)
```
- Keeps entire groups based on condition

---

## 📌 value_counts(normalize=True)
```python
df["day"].value_counts(normalize=True)
```
- Returns percentage distribution

---

## 📌 cut() / qcut()
```python
pd.cut(df["total_bill"], bins=[0, 10, 20, 40])
pd.qcut(df["tip"], q=4)
```
- `cut` → fixed bins
- `qcut` → equal distribution

---

# 4️⃣ Combining DataFrames

## 📌 merge() — SQL JOIN
```python
pd.merge(df1, df2, on="id", how="inner")
```

---

## 📌 join() — index-based merge
```python
df1.join(df2, how="left")
```

---

## 📌 concat() — stacking
```python
pd.concat([df1, df2], axis=0)
```
- axis=0 → rows
- axis=1 → columns

---

## 📌 explode() — flatten lists
```python
df.explode("tags")
```

---

# 5️⃣ Advanced Tricks

## 📌 apply()
```python
df["label"] = df["tip"].apply(lambda x: "High" if x > 5 else "Low")
```
- Custom logic
- Slower than vectorized ops

---

## 📌 mask() / where()
```python
df["tip"].mask(df["tip"] > 8, 8)
df["tip"].where(df["tip"] > 1, 1)
```
- Conditional replacement

---

## 📌 rank()
```python
df["rank"] = df.groupby("day")["tip"].rank(ascending=False)
```
- Ranking within groups

---

## 📌 pipe()
```python
df.pipe(func)
```
- Cleaner pipelines
- Improves readability

---

# 6️⃣ Strings, Dates & Cleaning

## 📌 String Operations (.str)
```python
df["day"].str.upper()
df["time"].str.contains("Dinner")
```
- Vectorized string processing

---

## 📌 to_datetime()
```python
df["date"] = pd.to_datetime(df["date"])
df["year"] = df["date"].dt.year
```
- Convert and extract date components

---

## 📌 Missing Data Handling
```python
df.isna()
df.fillna(df["col"].median())
df.dropna()
```
- Detect and handle null values

---

## 📌 astype()
```python
df["day"] = df["day"].astype("category")
```
- Memory optimization
- Faster computations

---

# 7️⃣ Visualization & Styling

## 📌 Plotting
```python
df.groupby("day")["tip"].mean().plot(kind="bar")
df["total_bill"].plot(kind="hist")
```
- Quick insights

---

## 📌 Styling
```python
df.style.background_gradient()
```
- Visual enhancement

---

# 8️⃣ Performance Tips

## 📌 memory_usage()
```python
df.memory_usage(deep=True)
```
- Check memory usage

---

## 📌 Chunking Large Files
```python
pd.read_csv("file.csv", chunksize=1000)
```
- Process large datasets efficiently

---

## 📌 Fast Access (.at / .iat)
```python
df.at[0, "col"]
df.iat[0, 1]
```
- Faster than `.loc`

---

# 🔥 Most Important Interview Concepts

- `query` vs boolean filtering
- `agg` vs `transform`
- `merge` vs `join` vs `concat`
- `cut` vs `qcut`
- `apply` vs vectorization

---

# 🧠 Mental Model

- **Row-wise → apply**
- **Group-wise → groupby**
- **Column-wise → vectorized ops**
- **Combine → merge / concat**
- **Filter → query / isin**

---

# 🚀 Final Tip

If you master:
- `groupby`
- `merge`
- `transform`

👉 You’re already ahead of 80% of beginners.
