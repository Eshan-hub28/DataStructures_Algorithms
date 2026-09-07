# 🌟 Taking 2D Array Inputs in Python

This guide explains the common patterns for reading a 2D array (matrix) from standard input in Python. These techniques are especially useful for competitive programming and solving coding challenges on platforms like LeetCode.

---

## 1️⃣ When you know the number of rows and columns beforehand

Suppose you want to read a **3 × 3 matrix**.

### Example Input
```text
1 2 3
4 5 6
7 8 9
```

### Python Code
```python
rows = 3
cols = 3

arr = []

for i in range(rows):
    # Read a line, split by space, convert to int, and make a list
    row = list(map(int, input().split()))
    arr.append(row)

print(arr)
```

### Example Output
```python
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

---

## 2️⃣ Taking rows and columns from the user

In this case, the first two inputs will dictate the dimensions of the matrix.

### Example Input
```text
3
3
1 2 3
4 5 6
7 8 9
```

### Python Code
```python
rows = int(input())
cols = int(input())

arr = []

for i in range(rows):
    row = list(map(int, input().split()))
    arr.append(row)

print(arr)
```

### Example Output
```python
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

---

## 🔍 Breaking Down the Code

> [!NOTE]
> Understanding this specific line is key to taking array inputs in Python:
>
> `row = list(map(int, input().split()))`

Here is a step-by-step breakdown of how it works for the input `"1 2 3"`:

1. **`input()`** → Reads the string `"1 2 3"`
2. **`split()`** → Splits the string into a list of strings: `["1", "2", "3"]`
3. **`map(int, ...)`** → Applies the `int` function to each item: `1, 2, 3`
4. **`list(...)`** → Converts the map object back into a list: `[1, 2, 3]`

Finally, **`arr.append(row)`** adds this newly created list as a row into our 2D array `arr`.
