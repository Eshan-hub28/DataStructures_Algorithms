# 1832. Check if the Sentence Is Pangram

## Algorithm Explanation
The algorithm checks whether a given string contains every letter of the English alphabet at least once. 
It can be solved using two approaches provided in the code:
1. **Boolean Array**: A boolean array of size 26 is used to keep track of seen characters. The algorithm iterates through the string, calculates the index of each character (`ch - 'a'`), and marks that index as `true`. Finally, it iterates through the boolean array to verify if all 26 values are `true`.
2. **HashSet**: A `HashSet` is used to store all unique characters in the sentence. The algorithm iterates through the string, adding each character to the set. Finally, it simply checks if the size of the set is exactly 26.

## Realistic Example (Input / Output)
**Input**: `sentence = "thequickbrownfoxjumpsoverthelazydog"`
**Output**: `true`
*(Explanation: The sentence contains at least one of every letter from 'a' to 'z'.)*

## Step-by-Step Dry Run (Boolean Array Approach)
Let's trace a short input `sentence = "abcc"` (Expected: false):
Initialize `seen` boolean array of size 26 to all `false`.

- **Iteration 1 (`i = 0`, `ch = 'a'`)**:
  - `seen['a' - 'a'] = seen[0] = true`.

- **Iteration 2 (`i = 1`, `ch = 'b'`)**:
  - `seen['b' - 'a'] = seen[1] = true`.

- **Iteration 3 (`i = 2`, `ch = 'c'`)**:
  - `seen['c' - 'a'] = seen[2] = true`.

- **Iteration 4 (`i = 3`, `ch = 'c'`)**:
  - `seen['c' - 'a'] = seen[2] = true` (already true).

- **Verification Step**:
  - Iterate `i` from 0 to 25.
  - `i = 3` (`'d'`) is `false`. Return `false`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the length of the string. We iterate through the string once, and then do a constant time check (iterating up to 26 times or checking the set size).
- **Space Complexity:** $O(1)$ because the extra space used is bounded by 26 (either a boolean array of size 26 or a HashSet holding at most 26 characters), regardless of how large the input string is.
