# Day 35 – Python Coding Challenge: Built-in Functions

A set of five short Python challenges focused on built-in functions and core data structures: lists, strings, sets, and dictionaries.

## Files

| File | Description |
|------|-------------|
| `Day35_Coding_Challenge.pdf` | Problem statements for all five challenges |
| `Day-35-Data-analytics-challenge-python.ipynb` | Jupyter Notebook with my solutions and outputs |

## Requirements

- Python 3.9+
- Jupyter Notebook or JupyterLab

No external libraries are needed.

## How to Run

```bash
jupyter notebook Day-35-Data-analytics-challenge-python.ipynb
```

Then run the cells in order (**Kernel → Restart & Run All**).

## Challenges

### 1. Flatten a Nested List
**Concepts:** list comprehension

Turn a list of lists into a single flat list.

```python
nested = [[1, 2], [3, 4], [5]]
# Output: [1, 2, 3, 4, 5]
```

**Approach:** Loop through each sublist, then through each item in it, appending to a result list.

**Alternative (list comprehension):**
```python
result = [j for i in nested for j in i]
```

---

### 2. Check Anagram
**Concepts:** `sorted()`

Check whether two strings contain the same letters.

```python
s1 = "listen"
s2 = "silent"
# Output: True
```

**Approach:** Sort the characters of both strings and compare the results.

```python
print(sorted(s1) == sorted(s2))
```

---

### 3. Find Missing Number
**Concepts:** `set()`

Find the number missing from a sequence.

```python
nums = [1, 2, 4, 5]
# Expected Output: 3
```

**Approach:** Build a set of the full range, then subtract the set of given numbers using set difference.

**Note:** The notebook prints `{3}` (a set). To get exactly `3` and avoid hardcoding the range:

```python
missing = set(range(1, max(nums) + 1)) - set(nums)
print(missing.pop())  # 3
```

---

### 4. Group Words by First Letter
**Concepts:** `dict`, `setdefault()`

Group words in a dictionary by their first letter.

```python
words = ["apple", "ant", "banana", "bat"]
# Output: {'a': ['apple', 'ant'], 'b': ['banana', 'bat']}
```

**Approach:** Use `setdefault()` to create an empty list for a new key, then append the word.

```python
groups = {}
for word in words:
    groups.setdefault(word[0], []).append(word)
```

---

### 5. Remove Empty Values
**Concepts:** dictionary comprehension

Remove keys whose values are `None`.

```python
data = {"a": 1, "b": None, "c": 3, "d": None}
# Output: {'a': 1, 'c': 3}
```

**Approach:** Rebuild the dictionary, keeping only items where the value is not `None`.

```python
result = {k: v for k, v in data.items() if v is not None}
```

## Key Takeaways

- `sorted()` is a quick way to compare strings by their characters.
- Set difference (`-`) is an efficient way to find missing items.
- `dict.setdefault()` simplifies grouping logic by removing the need for key-existence checks.
- List and dictionary comprehensions make filtering and flattening concise.

## Author

Day 35 of my Python / Data Analytics learning journey.
