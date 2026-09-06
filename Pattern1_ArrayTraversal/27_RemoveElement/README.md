# 27. Remove Element

## Algorithm Explanation
The algorithm removes all occurrences of a specific value (`val`) from an integer array (`nums`) in-place. It uses a two-pointer approach where `i` iterates through every element, and `index` keeps track of the position for the next valid element. If the current element is not equal to `val`, it is copied to the `index` position, and `index` is incremented. The function returns the new length of the array.

## Realistic Example (Input / Output)
**Input**: `nums = [3, 2, 2, 3]`, `val = 3`
**Output**: `2` (and the array `nums` is modified to `[2, 2, _, _]`)

## Step-by-Step Dry Run
Let's see how the algorithm processes the input `nums = [3, 2, 2, 3]` with `val = 3`:

- **Initialization**: `index = 0`

- **Iteration 1 (`i = 0`)**: 
  - `nums[0]` is `3`. 
  - Is `nums[0] != 3`? No.
  - Action: Do nothing. `index` remains `0`.

- **Iteration 2 (`i = 1`)**:
  - `nums[1]` is `2`.
  - Is `nums[1] != 3`? Yes.
  - Action: Set `nums[index] = nums[1]` (so `nums[0] = 2`).
  - Increment `index` to `1`.
  - Array state: `[2, 2, 2, 3]`

- **Iteration 3 (`i = 2`)**:
  - `nums[2]` is `2`.
  - Is `nums[2] != 3`? Yes.
  - Action: Set `nums[index] = nums[2]` (so `nums[1] = 2`).
  - Increment `index` to `2`.
  - Array state: `[2, 2, 2, 3]`

- **Iteration 4 (`i = 3`)**:
  - `nums[3]` is `3`.
  - Is `nums[3] != 3`? No.
  - Action: Do nothing. `index` remains `2`.

- **Final Step**: 
  - Loop finishes.
  - Return `index`, which is `2`. (The first two elements `[2, 2]` are the valid ones).

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the length of the array, since we iterate through the array exactly once.
- **Space Complexity:** $O(1)$ since the removal is done in-place without using any extra space.
