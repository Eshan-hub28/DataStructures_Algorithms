# 1431. Kids With the Greatest Number of Candies

## Algorithm Explanation
The algorithm aims to find out if each kid can have the greatest number of candies among all kids if they are given some `extraCandies`. 
1. It first makes one pass through the `candies` array to find the current maximum number of candies (`maxi`) any kid possesses.
2. It then iterates through the array a second time, checking if the current kid's candies plus the `extraCandies` is greater than or equal to the maximum (`maxi`) found in the first step.
3. If it is, `true` is added to the result list; otherwise, `false` is added.

## Realistic Example (Input / Output)
**Input**: `candies = [2, 3, 5, 1, 3]`, `extraCandies = 3`
**Output**: `[true, true, true, false, true]`

## Step-by-Step Dry Run
Let's see how the algorithm processes the input `candies = [2, 3, 5, 1, 3]` with `extraCandies = 3`:

- **Phase 1: Finding Maximum**
  - Initialize `maxi = 0`.
  - Check `2`: `max(0, 2) = 2`. `maxi = 2`.
  - Check `3`: `max(2, 3) = 3`. `maxi = 3`.
  - Check `5`: `max(3, 5) = 5`. `maxi = 5`.
  - Check `1`: `max(5, 1) = 5`. `maxi = 5`.
  - Check `3`: `max(5, 3) = 5`. `maxi = 5`.
  - *Final Maximum (`maxi`)* = `5`.

- **Phase 2: Checking condition**
  - **Kid 1 (`candies[0] = 2`)**: `2 + 3 (extra) = 5`. Is `5 >= maxi (5)`? Yes. Add `true`.
  - **Kid 2 (`candies[1] = 3`)**: `3 + 3 (extra) = 6`. Is `6 >= maxi (5)`? Yes. Add `true`.
  - **Kid 3 (`candies[2] = 5`)**: `5 + 3 (extra) = 8`. Is `8 >= maxi (5)`? Yes. Add `true`.
  - **Kid 4 (`candies[3] = 1`)**: `1 + 3 (extra) = 4`. Is `4 >= maxi (5)`? No. Add `false`.
  - **Kid 5 (`candies[4] = 3`)**: `3 + 3 (extra) = 6`. Is `6 >= maxi (5)`? Yes. Add `true`.

- **Final Step**: 
  - Return the list `[true, true, true, false, true]`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the number of kids. The array is iterated twice, giving $O(2N)$ which simplifies to $O(N)$.
- **Space Complexity:** $O(1)$ auxiliary space (ignoring the space required for the output list which is $O(N)$).
