# Java HashMap `entrySet()` - Complete Notes

## What is `entrySet()`?

A `HashMap` stores data in **key → value** pairs.

Example:

```java
HashMap<Integer, Integer> map = new HashMap<>();

map.put(1, 3);
map.put(2, 2);
map.put(5, 7);
```

The map contains:

| Key | Value |
|-----|------:|
| 1 | 3 |
| 2 | 2 |
| 5 | 7 |

---

# What does `entrySet()` return?

```java
map.entrySet()
```

returns a collection of **entries**.

Each entry contains:

- One key
- Its corresponding value

Think of it as:

```
Entry 1
---------
Key   = 1
Value = 3

Entry 2
---------
Key   = 2
Value = 2

Entry 3
---------
Key   = 5
Value = 7
```

---

# Syntax

```java
for (Map.Entry<Integer, Integer> entry : map.entrySet()) {

}
```

Let's understand every part.

---

## Part 1

```java
Map.Entry<Integer, Integer>
```

This is the **datatype**.

It represents **one key-value pair**.

Just like

```java
int x;
```

Here,

`int` is the datatype.

Similarly,

```java
Map.Entry<Integer, Integer> entry;
```

means

> `entry` stores one key-value pair.

---

## Part 2

```java
entry
```

This is simply the variable name.

It changes during every iteration.

---

## Part 3

```java
:
```

The colon means

> Take one item at a time from the collection.

Exactly like

```java
for(int num : arr)
```

where `num` stores one element of the array.

---

## Part 4

```java
map.entrySet()
```

This is the collection being traversed.

Internally it is like

```
[
 (1,3),
 (2,2),
 (5,7)
]
```

---

# Dry Run

Suppose

```java
HashMap<Integer,Integer> map = new HashMap<>();

map.put(1,3);
map.put(2,2);
map.put(5,7);
```

Loop:

```java
for (Map.Entry<Integer,Integer> entry : map.entrySet()) {

    System.out.println(entry.getKey());
    System.out.println(entry.getValue());
}
```

---

## First Iteration

```
entry

Key = 1
Value = 3
```

```
entry.getKey()   → 1
entry.getValue() → 3
```

---

## Second Iteration

```
entry

Key = 2
Value = 2
```

```
entry.getKey()   → 2
entry.getValue() → 2
```

---

## Third Iteration

```
entry

Key = 5
Value = 7
```

```
entry.getKey()   → 5
entry.getValue() → 7
```

---

# Visual Representation

```
HashMap

1 -----> 3

2 -----> 2

5 -----> 7
```

`entrySet()` converts it into

```
+-------------+
| Key = 1     |
| Value = 3   |
+-------------+

+-------------+
| Key = 2     |
| Value = 2   |
+-------------+

+-------------+
| Key = 5     |
| Value = 7   |
+-------------+
```

The loop visits one box at a time.

---

# Methods Available

## Get Key

```java
entry.getKey();
```

Returns

```text
1
2
5
```

---

## Get Value

```java
entry.getValue();
```

Returns

```text
3
2
7
```

---

# Example 1

Print every key and value.

```java
HashMap<Integer,Integer> map = new HashMap<>();

map.put(10,100);
map.put(20,200);
map.put(30,300);

for(Map.Entry<Integer,Integer> entry : map.entrySet()){

    System.out.println(
        entry.getKey() + " -> " + entry.getValue()
    );

}
```

Possible Output

```
10 -> 100
20 -> 200
30 -> 300
```

*(The order is not guaranteed because `HashMap` is unordered.)*

---

# Example 2

Find the maximum frequency.

```java
int maxFreq = 0;
int key = 0;

for(Map.Entry<Integer,Integer> entry : map.entrySet()){

    if(entry.getValue() > maxFreq){

        maxFreq = entry.getValue();
        key = entry.getKey();

    }
}
```

---

# Compare the Three Loops

## 1. keySet()

```java
for(int key : map.keySet()){

}
```

Gets only

```
Keys

1
2
5
```

To get the value

```java
map.get(key)
```

---

## 2. values()

```java
for(int value : map.values()){

}
```

Gets only

```
Values

3
2
7
```

You **cannot** know which key produced the value.

---

## 3. entrySet()

```java
for(Map.Entry<Integer,Integer> entry : map.entrySet()){

}
```

Gets both

```
Key = 1
Value = 3

Key = 2
Value = 2

Key = 5
Value = 7
```

No extra lookup required.

---

# When to Use What?

| Need | Use |
|------|-----|
| Only keys | `keySet()` |
| Only values | `values()` |
| Both key and value | `entrySet()` ⭐ |

---

# Common Interview Pattern

```java
for (Map.Entry<Integer, Integer> entry : map.entrySet()) {

    int key = entry.getKey();
    int value = entry.getValue();

    // Use key and value
}
```

---

# Key Takeaways

- A `HashMap` stores **key → value** pairs.
- `entrySet()` returns all key-value pairs.
- `entry.getKey()` returns the key.
- `entry.getValue()` returns the value.
- Use `entrySet()` whenever you need both the key and the value.
- It is preferred over `keySet()` + `map.get(key)` because it avoids an extra lookup.

---

# Memory Trick

Think of a dictionary:

```
Apple  -> 10
Mango  -> 20
Orange -> 15
```

- `keySet()` → Apple, Mango, Orange
- `values()` → 10, 20, 15
- `entrySet()` → Apple → 10, Mango → 20, Orange → 15

**Remember:**

> **entry = key + value together**