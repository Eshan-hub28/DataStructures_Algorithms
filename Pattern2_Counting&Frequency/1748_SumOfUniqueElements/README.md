# 1748. Sum of Unique Elements

## Algorithm Explanation
The algorithm computes the sum of all elements in an array that appear exactly once.
It uses a two-pass approach. In the first pass, it iterates over the array and uses a `HashMap` to store the frequency of each element (using the element as the key and its count as the value). In the second pass, it iterates through the keys of the `HashMap`. For each key, if its associated value (count) is exactly 1, the key is added to a running sum. Finally, the sum is returned.

## Realistic Example (Input / Output)
**Input**: `nums = [1, 2, 3, 2]`
**Output**: `4`
*(Explanation: The unique elements are 1 and 3. Their sum is 1 + 3 = 4. 2 is not unique because it appears twice.)*

## Step-by-Step Dry Run
Let's trace the input `nums = [1, 2, 3, 2]`:
Initialize an empty `map` and `sum = 0`.

- **Step 1 (Counting Frequencies)**:
  - `num = 1`: `map` becomes `{1: 1}`
  - `num = 2`: `map` becomes `{1: 1, 2: 1}`
  - `num = 3`: `map` becomes `{1: 1, 2: 1, 3: 1}`
  - `num = 2`: `map` becomes `{1: 1, 2: 2, 3: 1}`

- **Step 2 (Summing Unique Elements)**:
  - Iterate over keys: `[1, 2, 3]`
  - Key `1`: count is `1`. `sum += 1` $\rightarrow$ `sum = 1`.
  - Key `2`: count is `2`. Not unique. `sum = 1`.
  - Key `3`: count is `1`. `sum += 3` $\rightarrow$ `sum = 4`.

- **Final Step**:
  - Return `sum`: `4`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the number of elements in `nums`. We iterate through the array once and then through the unique elements in the map (which is at most $N$).
- **Space Complexity:** $O(N)$ because the `HashMap` can store up to $N$ key-value pairs if all elements in the array are distinct.
