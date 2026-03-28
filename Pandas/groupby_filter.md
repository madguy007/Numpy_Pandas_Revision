# 📊 Active Businesses — Your Approach (Pandas Summary)

## 🧾 Problem Statement

Identify **active businesses**.

A business is **active** if:

* It has **more than one event type**, and
* The **occurrences for those event types are greater than the average occurrences** of that event type across all businesses

---

## 📥 Input

```python
events = pd.DataFrame({
    'business_id': [1, 3, 1, 2, 3, 1, 2],
    'event_type': ['reviews', 'reviews', 'ads', 'ads', 'ads', 'page views', 'page views'],
    'occurrences': [7, 3, 11, 7, 6, 3, 12]
})
```

---

## 🧠 Concepts Used

* `groupby()` → aggregation
* `mean()` → compute averages
* `merge()` → combine datasets
* Column renaming (`rename`)
* Boolean filtering
* `nunique()` → distinct event count
* Conditional filtering

---

## 🏷️ Problem Type

**GroupBy → Aggregate → Merge → Filter → GroupBy → Filter**

---

## 🪜 Your Step-by-Step Code

```python
event_avg = events.groupby('event_type')['occurrences'].mean().reset_index()

business = pd.merge(events, event_avg, on='event_type')

business.rename(columns={
    'occurrences_x': 'occurrences',
    'occurrences_y': 'event_avg'
}, inplace=True)

business = business[business['occurrences'] > business['event_avg']]

result = business.groupby('business_id')['event_type'].nunique().reset_index()

result = result[result['event_type'] > 1]

print(result[['business_id']])
```

---

## ⚠️ Mistake You Faced

```python
.drop('event_avg', axis=1)
```

---

## 🧠 Pattern Breakdown

```text
1. Group by event_type → get average
2. Merge → attach average to each row
3. Filter → occurrences > average
4. Group by business → count event types
5. Filter → more than 1 event type
```

---

## 🚀 Tips for Similar Questions

### ✅ Tip 1: Spot the pattern

If question says:

* "greater than average"
* "compared to others"

👉 Always:

```text
groupby → aggregate → merge → filter
```

---

### ✅ Tip 2: Don’t confuse variable vs column

* `event_avg` (DataFrame) ≠ `'event_avg'` (column)

---

### ✅ Tip 3: Use `nunique()` for distinct logic

* “more than one type” → `nunique()`

---

### ✅ Tip 4: Order matters

```text
merge → rename → filter
```

Not:

```text
merge → drop → rename ❌
```

---

## 🧠 One-Line Insight

👉 **Attach group metrics → filter rows → aggregate again → filter entities**

---
