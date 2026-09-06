# 1470. Shuffle the Array

## Algorithm Explanation
The algorithm receives an array consisting of $2n$ elements in the form `[x1, x2, ..., xn, y1, y2, ..., yn]`. It needs to shuffle the array into `[x1, y1, x2, y2, ..., xn, yn]`. 
It accomplishes this by creating a new array `arr` of the same size. It uses two pointers for the target array: `k` (starting at 0 for even indices) and `j` (starting at 1 for odd indices). As it iterates through the original array `nums`:
- The first half of `nums` (where `i < n`) is placed into the even positions (`arr[k]`).
- The second half of `nums` (where `i >= n`) is placed into the odd positions (`arr[j]`).
Both pointers `k` and `j` are incremented by 2 after each insertion.

## Realistic Example (Input / Output)
**Input**: `nums = [2, 5, 1, 3, 4, 7]`, `n = 3`
**Output**: `[2, 3, 5, 4, 1, 7]`
*(Explanation: The array is split into two halves `[2, 5, 1]` and `[3, 4, 7]`. We weave them together: `2` then `3`, `5` then `4`, `1` then `7`.)*

## Step-by-Step Dry Run
Let's trace the input `nums = [2, 5, 1, 3, 4, 7]` with `n = 3`:
`nums.length = 6`. Create new array `arr = [0, 0, 0, 0, 0, 0]`.
Pointers: `k = 0`, `j = 1`.

- **Iteration 1 (`i = 0`)**: 
  - `i < 3` is True.
  - `arr[k] = nums[0]` $\rightarrow$ `arr[0] = 2`.
  - `k` becomes `2`.
  - Array state: `[2, 0, 0, 0, 0, 0]`

- **Iteration 2 (`i = 1`)**:
  - `i < 3` is True.
  - `arr[k] = nums[1]` $\rightarrow$ `arr[2] = 5`.
  - `k` becomes `4`.
  - Array state: `[2, 0, 5, 0, 0, 0]`

- **Iteration 3 (`i = 2`)**:
  - `i < 3` is True.
  - `arr[k] = nums[2]` $\rightarrow$ `arr[4] = 1`.
  - `k` becomes `6`.
  - Array state: `[2, 0, 5, 0, 1, 0]`

- **Iteration 4 (`i = 3`)**:
  - `i < 3` is False.
  - `arr[j] = nums[3]` $\rightarrow$ `arr[1] = 3`.
  - `j` becomes `3`.
  - Array state: `[2, 3, 5, 0, 1, 0]`

- **Iteration 5 (`i = 4`)**:
  - `i < 3` is False.
  - `arr[j] = nums[4]` $\rightarrow$ `arr[3] = 4`.
  - `j` becomes `5`.
  - Array state: `[2, 3, 5, 4, 1, 0]`

- **Iteration 6 (`i = 5`)**:
  - `i < 3` is False.
  - `arr[j] = nums[5]` $\rightarrow$ `arr[5] = 7`.
  - `j` becomes `7`.
  - Array state: `[2, 3, 5, 4, 1, 7]`

- **Final Step**: 
  - Return `arr`: `[2, 3, 5, 4, 1, 7]`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the total length of the array (`2n`). We iterate exactly once.
- **Space Complexity:** $O(N)$ because a new array `arr` of size $2n$ is created to store the answer.
