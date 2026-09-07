# 771. Jewels and Stones

## Algorithm Explanation
The algorithm determines how many of the given `stones` are also `jewels`.
It uses a brute-force approach with nested loops. An outer loop iterates through each character in the `jewels` string, and an inner loop iterates through each character in the `stones` string. Whenever a stone matches the current jewel, a counter is incremented. After comparing all jewels with all stones, the final count represents the total number of jewels among the stones.

## Realistic Example (Input / Output)
**Input**: `jewels = "aA"`, `stones = "aAAbbbb"`
**Output**: `3`
*(Explanation: The jewels are 'a' and 'A'. In the stones string, we have one 'a' and two 'A's. So there are 1 + 2 = 3 jewels in total.)*

## Step-by-Step Dry Run
Let's trace the input `jewels = "aA"`, `stones = "aAAb"`:
Initialize `count = 0`.

- **Outer Iteration 1 (`i = 0`, `jewels[0] = 'a'`)**:
  - Inner loop over `stones = "aAAb"`:
  - `j = 0, stones[0] = 'a'`: Match! `count` $\rightarrow$ 1.
  - `j = 1, stones[1] = 'A'`: No match.
  - `j = 2, stones[2] = 'A'`: No match.
  - `j = 3, stones[3] = 'b'`: No match.

- **Outer Iteration 2 (`i = 1`, `jewels[1] = 'A'`)**:
  - Inner loop over `stones = "aAAb"`:
  - `j = 0, stones[0] = 'a'`: No match.
  - `j = 1, stones[1] = 'A'`: Match! `count` $\rightarrow$ 2.
  - `j = 2, stones[2] = 'A'`: Match! `count` $\rightarrow$ 3.
  - `j = 3, stones[3] = 'b'`: No match.

- **Final Step**:
  - Return `count`: `3`.

## Performance Analysis
- **Time Complexity:** $O(J \times S)$ where $J$ is the length of `jewels` and $S$ is the length of `stones`. For each jewel character, we iterate through the entire stones string. 
- **Space Complexity:** $O(1)$ because only a single `count` variable is used, taking constant extra space regardless of the input sizes. *(Note: A more optimal approach using a HashSet would have $O(J + S)$ time complexity and $O(J)$ space complexity, but the current brute-force implementation is $O(J \times S)$ time and $O(1)$ space.)*
