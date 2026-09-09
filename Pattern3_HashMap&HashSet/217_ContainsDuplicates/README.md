# 217. Contains Duplicate

## Algorithm Explanation
The algorithm checks if an array contains any duplicate elements.
It uses a `HashSet` to keep track of the elements we have seen so far. As we iterate through the array `nums`, we check if the current element is already present in the `HashSet`. If it is, we have found a duplicate and return `true`. If not, we add the element to the `HashSet`. If the loop finishes without finding any duplicates, we return `false`.

## Realistic Example (Input / Output)
**Input**: `nums = [1, 2, 3, 1]`
**Output**: `true`
*(Explanation: The element `1` appears twice in the array.)*

## Step-by-Step Dry Run
Let's trace the input `nums = [1, 2, 3, 1]`:
- **Step 1**:
  - `i = 0`: element `1` is not in set. Add to set $\rightarrow$ `set = {1}`.
- **Step 2**:
  - `i = 1`: element `2` is not in set. Add to set $\rightarrow$ `set = {1, 2}`.
- **Step 3**:
  - `i = 2`: element `3` is not in set. Add to set $\rightarrow$ `set = {1, 2, 3}`.
- **Step 4**:
  - `i = 3`: element `1` is already in set! Return `true`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the number of elements in the array. We iterate through the array once and `HashSet` lookups/insertions are $O(1)$ on average.
- **Space Complexity:** $O(N)$ because in the worst-case (all unique elements), the `HashSet` will store $N$ elements.
