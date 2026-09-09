# 242. Valid Anagram

## Algorithm Explanation
The algorithm checks if two strings `s` and `t` are anagrams (i.e., they contain the exact same characters with the exact same frequencies).
We can use a `HashMap` or a character frequency array (since the input consists of lowercase English letters) to count the occurrences of each character in string `s`. Then, we iterate through string `t` and decrement the counts for each character. If the strings are of unequal length, they can't be anagrams. After adjusting counts, if any count does not match or drops below zero, they are not anagrams.

## Realistic Example (Input / Output)
**Input**: `s = "anagram"`, `t = "nagaram"`
**Output**: `true`
*(Explanation: Both strings contain 'a' 3 times, 'n' 1 time, 'g' 1 time, 'r' 1 time, and 'm' 1 time.)*

## Step-by-Step Dry Run
Let's trace the input `s = "rat", t = "car"`:
- **Length Check**: Both have length 3.
- **Step 1 (Counting `s`)**:
  - `s = "rat"`: Increment frequencies. `map = {'r': 1, 'a': 1, 't': 1}`.
- **Step 2 (Decrements from `t`)**:
  - `i = 0`, `ch = 'c'`: `'c'` is not in map or its frequency drops below 0. Return `false`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the length of the strings. We iterate through the strings to populate and check the character counts.
- **Space Complexity:** $O(1)$ space since the alphabet size is fixed to 26 lowercase English letters.
