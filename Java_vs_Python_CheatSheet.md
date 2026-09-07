# Java vs Python Cheat Sheet

A comprehensive mapping of common data structures, syntax, and logic patterns used in LeetCode problems when switching from Java to Python.

---

## 1. Hash Maps (Java) vs Dictionaries (Python)

### Initialization
**Java:**
```java
HashMap<Integer, Integer> map = new HashMap<>();
```
**Python:**
```python
freq = {}
```

### Inserting / Updating with a Default Value
**Java:**
```java
map.put(num, map.getOrDefault(num, 0) + 1);
```
**Python:**
```python
freq[num] = freq.get(num, 0) + 1
```
> **Python `get()` method:** `freq.get(num, 0)` is highly useful. It means: *"Give me the value of `num` if it exists, otherwise give me `0`."*

### Iterating over Values
**Java:**
```java
for (int count : map.values()) { ... }
```
**Python:**
```python
for count in freq.values(): ...
```

### Iterating over Keys
**Java:**
```java
for (int key : map.keySet()) { ... }
```
**Python:**
```python
for key in freq.keys(): ...
# OR simply:
for key in freq: ...
```

### Iterating over Key-Value Pairs
**Java:**
```java
for (Map.Entry<Integer, Integer> entry : map.entrySet()) {
    int key = entry.getKey();
    int value = entry.getValue();
}
```
**Python:**
```python
for key, value in freq.items(): ...
```

---

## 2. Hash Sets (Java) vs Sets (Python)

### Initialization
**Java:**
```java
HashSet<Integer> seen = new HashSet<>();
```
**Python:**
```python
seen = set()
```
> **Warning:** Do not use `seen = {}` to create an empty set in Python; that creates an empty dictionary! Always use `set()`.

### Adding an Element
**Java:**
```java
seen.add(count);
```
**Python:**
```python
seen.add(count)
```

### Checking if an Element Exists (Contains)
**Java:**
```java
if (seen.contains(count)) { ... }
```
**Python:**
```python
if count in seen: ...
```

### Removing an Element
**Java:**
```java
seen.remove(count);
```
**Python:**
```python
seen.discard(count) # Safely removes, does nothing if 'count' is missing
# OR
seen.remove(count)  # Removes, but raises a KeyError if 'count' is missing
```

---

## 3. Arrays (Java) vs Lists (Python)

### Initialization
**Java:**
```java
int[] arr = new int[5]; // Array (Fixed size)
List<Integer> list = new ArrayList<>(); // ArrayList (Dynamic)
```
**Python:**
```python
arr = [0] * 5 # Fixed size equivalent
lst = [] # Dynamic size
```

### Getting Length
**Java:**
```java
int n = arr.length;  // Array
int m = list.size(); // ArrayList
```
**Python:**
```python
n = len(arr)
```

### Appending Elements
**Java:**
```java
list.add(5); // ArrayList
```
**Python:**
```python
lst.append(5)
```

---

## 4. Loops and Iteration

### Iterating over Elements (Enhanced For-Loop)
**Java:**
```java
for (int num : arr) { ... }
```
**Python:**
```python
for num in arr: ...
```

### Iterating with Index (Standard For-Loop)
**Java:**
```java
for (int i = 0; i < arr.length; i++) {
    int num = arr[i];
}
```
**Python:**
```python
for i in range(len(arr)):
    num = arr[i]
```

### Iterating with Both Index and Element
**Java:**
```java
for (int i = 0; i < arr.length; i++) {
    int num = arr[i];
    // Do something with i and num
}
```
**Python:**
```python
for i, num in enumerate(arr):
    # 'enumerate' gives you both the index and the element automatically
    ...
```

---

## 5. Strings and Characters

### Accessing a Character by Index
**Java:**
```java
char ch = s.charAt(i);
```
**Python:**
```python
ch = s[i]
```

### Checking Substrings
**Java:**
```java
if (s.contains("abc")) { ... }
```
**Python:**
```python
if "abc" in s: ...
```
