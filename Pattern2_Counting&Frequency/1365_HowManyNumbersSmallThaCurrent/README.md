# 1365. How Many Numbers Are Smaller Than the Current Number

## Algorithm Explanation
The algorithm calculates, for each element in the given array `nums`, how many elements are strictly smaller than it.
It accomplishes this using a brute-force approach. An output array `ans` of the same length as `nums` is created. For every element `nums[i]`, a nested loop iterates through all the elements `nums[j]` in the array. If `nums[i] > nums[j]`, a counter is incremented. After comparing `nums[i]` with all other elements, the count is stored in `ans[i]`. 

## Realistic Example (Input / Output)
**Input**: `nums = [8, 1, 2, 2, 3]`
**Output**: `[4, 0, 1, 1, 3]`
*(Explanation: For 8, there are four smaller numbers (1, 2, 2, 3). For 1, there are none. For 2, there is one smaller number (1). For 3, there are three smaller numbers (1, 2, 2).)*

## Step-by-Step Dry Run
Let's trace the input `nums = [8, 1, 2, 2, 3]`:
`nums.length = 5`. Create new array `ans = [0, 0, 0, 0, 0]`.

- **Iteration 1 (`i = 0`, `nums[0] = 8`)**:
  - Compare with all: `8 > 1`, `8 > 2`, `8 > 2`, `8 > 3`.
  - Count = 4.
  - `ans[0] = 4`. `ans` state: `[4, 0, 0, 0, 0]`

- **Iteration 2 (`i = 1`, `nums[1] = 1`)**:
  - Compare with all: `1` is not greater than any other element.
  - Count = 0.
  - `ans[1] = 0`. `ans` state: `[4, 0, 0, 0, 0]`

- **Iteration 3 (`i = 2`, `nums[2] = 2`)**:
  - Compare with all: `2 > 1`.
  - Count = 1.
  - `ans[2] = 1`. `ans` state: `[4, 0, 1, 0, 0]`

- **Iteration 4 (`i = 3`, `nums[3] = 2`)**:
  - Compare with all: `2 > 1`.
  - Count = 1.
  - `ans[3] = 1`. `ans` state: `[4, 0, 1, 1, 0]`

- **Iteration 5 (`i = 4`, `nums[4] = 3`)**:
  - Compare with all: `3 > 1`, `3 > 2`, `3 > 2`.
  - Count = 3.
  - `ans[4] = 3`. `ans` state: `[4, 0, 1, 1, 3]`

- **Final Step**:
  - Return `ans`: `[4, 0, 1, 1, 3]`.

## Performance Analysis
- **Time Complexity:** $O(N^2)$ where $N$ is the length of `nums`. There are two nested loops both iterating $N$ times.
- **Space Complexity:** $O(N)$ for the output array `ans` that stores the result.
