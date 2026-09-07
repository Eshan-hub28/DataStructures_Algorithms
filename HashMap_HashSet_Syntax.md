# HashMap and HashSet Syntax in Java

This document explains the common syntax and usage of `HashMap` and `HashSet` in Java, specifically focusing on frequency counting and uniqueness checks, as seen in many LeetCode problems.

## 1. Frequency Counting with `HashMap`

A common pattern is to count how many times each element appears in an array. We use a `HashMap` where the **key** is the element and the **value** is its frequency.

```java
// 1. Initialize the HashMap
HashMap<Integer, Integer> map = new HashMap<>();

// 2. Iterate through the array using an enhanced for-loop
for(int num : arr) {
    // 3. Update the frequency count
    map.put(num, map.getOrDefault(num, 0) + 1);
}
```

### Breakdown:
*   **`HashMap<Integer, Integer> map = new HashMap<>();`**: Creates a new, empty HashMap. We specify `<Integer, Integer>` meaning both the keys (the numbers from the array) and the values (their counts) will be integers.
*   **`for(int num : arr)`**: This is an enhanced for-loop (or "for-each" loop). It iterates through every element in the array `arr`. In each iteration, `num` takes the value of the current element.
*   **`map.getOrDefault(num, 0)`**: This is the most crucial part. It looks for the key `num` in the map.
    *   If `num` is **already in the map**, it returns its current count.
    *   If `num` is **not in the map** yet, it returns the default value, which we set to `0`.
*   **`+ 1`**: We add 1 to whatever `getOrDefault` returned.
*   **`map.put(key, value)`**: This inserts or updates the key-value pair in the map. So, we are putting `num` back into the map with its new, incremented count.

## 2. Checking Uniqueness with `HashSet`

A `HashSet` is a collection that contains no duplicate elements. It's highly efficient for checking if you have "seen" an element before.

```java
// 1. Initialize the HashSet
HashSet<Integer> seen = new HashSet<>();

// 2. Iterate over the values of the HashMap
for(int num : map.values()) {
    // 3. Check if the HashSet already contains the value
    if(seen.contains(num)) {
        return false; // Found a duplicate!
    }
    // 4. Add the unique value to the HashSet
    seen.add(num);
}
```

### Breakdown:
*   **`HashSet<Integer> seen = new HashSet<>();`**: Creates a new, empty HashSet designed to hold Integers.
*   **`map.values()`**: This method returns a collection of all the *values* currently stored in the HashMap (in our case, the frequency counts).
*   **`for(int num : map.values())`**: We iterate through each of those frequency counts. Here, `num` represents a frequency count.
*   **`seen.contains(num)`**: This method returns `true` if the HashSet `seen` already contains `num`. Since HashSets don't allow duplicates, if `contains` is true, it means we've encountered this exact frequency before.
*   **`seen.add(num)`**: If the number wasn't in the HashSet, we add it. The next time this same number appears, `seen.contains()` will evaluate to `true`.
