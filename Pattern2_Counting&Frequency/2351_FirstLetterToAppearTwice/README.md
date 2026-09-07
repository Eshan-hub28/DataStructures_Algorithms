# 2351. First Letter to Appear Twice

## Algorithm Explanation
The algorithm finds the first character in a string that appears for a second time.
It uses an integer array `freq` of size 26 to keep track of the frequency of each lowercase English letter. As it iterates through the string character by character, it calculates the index for the current character (`ch - 'a'`) and increments its count in the `freq` array. Immediately after incrementing, it checks if the count has reached 2. If it has, this character is the first one to appear twice, and it is returned immediately.

## Realistic Example (Input / Output)
**Input**: `s = "abccbaacz"`
**Output**: `'c'`
*(Explanation: The letter 'a' appears on the indices 0, 5 and 6. The letter 'b' appears on the indices 1 and 4. The letter 'c' appears on the indices 2, 3 and 7. The letter 'z' appears on the index 8. The letter 'c' is the first letter to appear twice, because out of all the letters the index of its second occurrence is the smallest.)*

## Step-by-Step Dry Run
Let's trace the input `s = "abcc"`:
Initialize `freq` array of size 26 to all zeros.

- **Iteration 1 (`i = 0`, `ch = 'a'`)**:
  - `freq['a' - 'a']++` $\rightarrow$ `freq[0] = 1`.
  - Is `freq[0] == 2`? No.

- **Iteration 2 (`i = 1`, `ch = 'b'`)**:
  - `freq['b' - 'a']++` $\rightarrow$ `freq[1] = 1`.
  - Is `freq[1] == 2`? No.

- **Iteration 3 (`i = 2`, `ch = 'c'`)**:
  - `freq['c' - 'a']++` $\rightarrow$ `freq[2] = 1`.
  - Is `freq[2] == 2`? No.

- **Iteration 4 (`i = 3`, `ch = 'c'`)**:
  - `freq['c' - 'a']++` $\rightarrow$ `freq[2] = 2`.
  - Is `freq[2] == 2`? Yes. Return `'c'`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the length of the string `s`. In the worst case, we might iterate through the entire string (although realistically, the loop will terminate in at most 27 iterations due to the Pigeonhole Principle).
- **Space Complexity:** $O(1)$ because the size of the `freq` array is fixed at 26, irrespective of the length of the string.
