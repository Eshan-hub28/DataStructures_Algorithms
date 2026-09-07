# 1207. Unique Number of Occurrences

## Algorithm Explanation
The algorithm takes an array `arr` and determines if the frequency of each unique element is itself unique.
It first uses a `HashMap` to count the occurrences of each element in the array. The keys are the elements, and the values are their frequencies.
Next, it iterates over all the frequency values obtained from the map and uses a `HashSet` to keep track of the frequencies seen so far. If a frequency is already present in the `HashSet`, it means two different elements have the same frequency, so it returns `false`. If the loop finishes without finding any duplicate frequencies, it returns `true`.

## Realistic Example (Input / Output)
**Input**: `arr = [1, 2, 2, 1, 1, 3]`
**Output**: `true`
*(Explanation: The value `1` has 3 occurrences, `2` has 2, and `3` has 1. No two values have the same number of occurrences.)*

## Step-by-Step Dry Run
Let's trace the input `arr = [1, 2, 2, 1, 1, 3]`:
- **Step 1 (Counting Frequencies)**:
  - Iterate through `arr`:
  - `i = 0`: `map = {1: 1}`
  - `i = 1`: `map = {1: 1, 2: 1}`
  - `i = 2`: `map = {1: 1, 2: 2}`
  - `i = 3`: `map = {1: 2, 2: 2}`
  - `i = 4`: `map = {1: 3, 2: 2}`
  - `i = 5`: `map = {1: 3, 2: 2, 3: 1}`

- **Step 2 (Checking Unique Frequencies)**:
  - Iterate over map values: `[3, 2, 1]`
  - Current value `3`: not in `seen`, add to `seen` $\rightarrow$ `seen = {3}`
  - Current value `2`: not in `seen`, add to `seen` $\rightarrow$ `seen = {3, 2}`
  - Current value `1`: not in `seen`, add to `seen` $\rightarrow$ `seen = {3, 2, 1}`

- **Final Step**: 
  - Loop finishes, return `true`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the total number of elements in `arr`. We iterate through the array once to populate the map, and once over the map's values which is at most $N$.
- **Space Complexity:** $O(N)$ because in the worst-case (all unique elements), the `HashMap` and `HashSet` will each store $N$ elements.
