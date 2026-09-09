# 389. Find the Difference

## Algorithm Explanation
The algorithm finds the one character that was added to string `t` when string `s` was randomly shuffled.
There are a few ways to solve this. A common `HashMap`/frequency array approach counts the occurrences of characters in `s` and then subtracts counts while iterating through `t`. The character that drops below zero or isn't found is the extra character. Another optimal approach involves summing the ASCII values of characters in `t` and subtracting the sum of ASCII values of characters in `s`. The remaining difference is the ASCII value of the added character.

## Realistic Example (Input / Output)
**Input**: `s = "abcd"`, `t = "abcde"`
**Output**: `"e"`
*(Explanation: 'e' is the letter that was added.)*

## Step-by-Step Dry Run
Let's trace `s = "abcd", t = "abcde"` using the ASCII sum approach:
- **Step 1 (Sum `s`)**:
  - `sumS = 97 + 98 + 99 + 100 = 394` (ASCII values for a, b, c, d)
- **Step 2 (Sum `t`)**:
  - `sumT = 97 + 98 + 99 + 100 + 101 = 495`
- **Final Step**: 
  - Difference `sumT - sumS = 495 - 394 = 101`.
  - ASCII value `101` corresponds to the character `'e'`. Return `'e'`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the length of the string. We iterate through both strings once.
- **Space Complexity:** $O(1)$ space since we only store sums in variables (or if using a frequency array, it takes fixed space for 26 characters).
