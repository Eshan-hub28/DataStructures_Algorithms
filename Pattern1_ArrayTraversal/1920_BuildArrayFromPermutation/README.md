# 1920. Build Array from Permutation

## Algorithm Explanation
The algorithm builds a new array (`ans`) of the same length as a given zero-based permutation array `nums`. For every index `i`, it assigns the value of `nums[nums[i]]` to `ans[i]`. It does this by creating a new integer array and using a single `for` loop to iterate from `0` to `nums.length - 1`, setting each element respectively, and then returning the newly constructed array.

## Realistic Example (Input / Output)
**Input**: `nums = [0, 2, 1, 5, 3, 4]`
**Output**: `[0, 1, 2, 4, 5, 3]`
*(Explanation: `ans[0] = nums[nums[0]] = nums[0] = 0`. `ans[1] = nums[nums[1]] = nums[2] = 1`, etc.)*

## Step-by-Step Dry Run
Let's see how the algorithm processes the input `nums = [0, 2, 1, 5, 3, 4]`:

- **Initialization**: 
  - `nums.length = 6`. 
  - Allocate new array `ans = [0, 0, 0, 0, 0, 0]`.

- **Loop Execution (`i` from 0 to 5)**: 
  - **`i = 0`**: `ans[0] = nums[nums[0]]` -> `nums[0]` is `0`. So, `ans[0] = nums[0] = 0`.
  - **`i = 1`**: `ans[1] = nums[nums[1]]` -> `nums[1]` is `2`. So, `ans[1] = nums[2] = 1`.
  - **`i = 2`**: `ans[2] = nums[nums[2]]` -> `nums[2]` is `1`. So, `ans[2] = nums[1] = 2`.
  - **`i = 3`**: `ans[3] = nums[nums[3]]` -> `nums[3]` is `5`. So, `ans[3] = nums[5] = 4`.
  - **`i = 4`**: `ans[4] = nums[nums[4]]` -> `nums[4]` is `3`. So, `ans[4] = nums[3] = 5`.
  - **`i = 5`**: `ans[5] = nums[nums[5]]` -> `nums[5]` is `4`. So, `ans[5] = nums[4] = 3`.

- **Final Step**: 
  - Loop terminates. Return `ans` which is `[0, 1, 2, 4, 5, 3]`.

## Performance Analysis
- **Time Complexity:** $O(N)$, where $N$ is the number of elements in `nums`. We traverse the array exactly once.
- **Space Complexity:** $O(N)$ for creating the new array `ans` of size $N$ to store the result.
