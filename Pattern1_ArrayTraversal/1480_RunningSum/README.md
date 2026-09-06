# 1480. Running Sum of 1d Array

## Algorithm Explanation
The algorithm calculates the "running sum" of an array. A running sum at index `i` is defined as the sum of all elements from index `0` up to index `i`. 
It does this by maintaining a `sum` variable, initialized to `0`. It iterates through the input array, adds the current element to `sum`, and stores this updated sum into a new array `a` at the same index. 

## Realistic Example (Input / Output)
**Input**: `nums = [1, 2, 3, 4]`
**Output**: `[1, 3, 6, 10]`
*(Explanation: Running sums are `[1, 1+2, 1+2+3, 1+2+3+4]`)*

## Step-by-Step Dry Run
Let's see how the algorithm processes the input `nums = [1, 2, 3, 4]`:
`nums.length = 4`. Create a new array `a = [0, 0, 0, 0]`.
Initialize `sum = 0`.

- **Iteration 1 (`i = 0`)**: 
  - `sum += nums[0]` $\rightarrow$ `sum = 0 + 1 = 1`.
  - `a[0] = 1`.
  - Array `a` state: `[1, 0, 0, 0]`

- **Iteration 2 (`i = 1`)**:
  - `sum += nums[1]` $\rightarrow$ `sum = 1 + 2 = 3`.
  - `a[1] = 3`.
  - Array `a` state: `[1, 3, 0, 0]`

- **Iteration 3 (`i = 2`)**:
  - `sum += nums[2]` $\rightarrow$ `sum = 3 + 3 = 6`.
  - `a[2] = 6`.
  - Array `a` state: `[1, 3, 6, 0]`

- **Iteration 4 (`i = 3`)**:
  - `sum += nums[3]` $\rightarrow$ `sum = 6 + 4 = 10`.
  - `a[3] = 10`.
  - Array `a` state: `[1, 3, 6, 10]`

- **Final Step**: 
  - Loop finishes.
  - Return `a`, which is `[1, 3, 6, 10]`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the number of elements in `nums`. We perform exactly one pass over the array.
- **Space Complexity:** $O(N)$ to store the output array `a` (though in some strict space complexity definitions where output space is not counted, this could be considered $O(1)$ auxiliary space).
