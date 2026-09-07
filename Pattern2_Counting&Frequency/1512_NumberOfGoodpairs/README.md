# 1512. Number of Good Pairs

## Algorithm Explanation
The algorithm finds the total number of "good pairs" in an array. A pair `(i, j)` is considered good if `nums[i] == nums[j]` and `i < j`.
It solves this using a brute-force double loop. The outer loop iterates through each element at index `i`. The inner loop starts at `i + 1` and iterates to the end of the array (at index `j`). Whenever `nums[i]` matches `nums[j]`, it increments a `count` variable. This guarantees that all pairs are checked exactly once, and since `j` starts at `i + 1`, the condition `i < j` is always satisfied.

## Realistic Example (Input / Output)
**Input**: `nums = [1, 2, 3, 1, 1, 3]`
**Output**: `4`
*(Explanation: The good pairs are (0,3), (0,4), (3,4), (2,5) using 0-based indexing. For example, `nums[0] == nums[3]` which is `1 == 1`.)*

## Step-by-Step Dry Run
Let's trace the input `nums = [1, 2, 3, 1, 1, 3]`:
Initialize `count = 0`.

- **Outer Iteration 1 (`i = 0, nums[i] = 1`)**:
  - Compare with `nums[1]` to `nums[5]`: `2, 3, 1, 1, 3`
  - Matches at `j = 3` (val `1`). `count` $\rightarrow$ 1
  - Matches at `j = 4` (val `1`). `count` $\rightarrow$ 2

- **Outer Iteration 2 (`i = 1, nums[i] = 2`)**:
  - Compare with `nums[2]` to `nums[5]`: `3, 1, 1, 3`
  - No matches. `count` remains 2.

- **Outer Iteration 3 (`i = 2, nums[i] = 3`)**:
  - Compare with `nums[3]` to `nums[5]`: `1, 1, 3`
  - Matches at `j = 5` (val `3`). `count` $\rightarrow$ 3

- **Outer Iteration 4 (`i = 3, nums[i] = 1`)**:
  - Compare with `nums[4]` to `nums[5]`: `1, 3`
  - Matches at `j = 4` (val `1`). `count` $\rightarrow$ 4

- **Outer Iteration 5 (`i = 4, nums[i] = 1`)**:
  - Compare with `nums[5]`: `3`
  - No matches. `count` remains 4.

- **Final Step**:
  - Return `count`: `4`.

## Performance Analysis
- **Time Complexity:** $O(N^2)$ where $N$ is the number of elements in `nums`. We check all possible pairs, which takes $N \times (N-1) / 2$ operations.
- **Space Complexity:** $O(1)$ because only a single `count` variable is used, taking constant extra space regardless of the input size.
