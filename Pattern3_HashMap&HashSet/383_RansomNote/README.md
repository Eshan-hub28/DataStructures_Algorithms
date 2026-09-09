# 383. Ransom Note

## Algorithm Explanation
The algorithm checks if the `ransomNote` can be constructed using the letters from `magazine`. Each letter from `magazine` can only be used once.
It uses a `HashMap` (or an integer array of size 26) to count the frequencies of each character in `magazine`. Then, it iterates through the characters in `ransomNote` and decrements their corresponding counts in the map. If a character is not found or its count drops below zero, it means we don't have enough letters, so it returns `false`. If we can iterate through the entire `ransomNote`, we return `true`.

## Realistic Example (Input / Output)
**Input**: `ransomNote = "aa"`, `magazine = "aab"`
**Output**: `true`
*(Explanation: The magazine has two 'a's and one 'b'. We can construct "aa" using the two 'a's.)*

## Step-by-Step Dry Run
Let's trace `ransomNote = "aa", magazine = "ab"`:
- **Step 1 (Count magazine)**:
  - Iterate through `"ab"`: `counts = {'a': 1, 'b': 1}`.
- **Step 2 (Check ransomNote)**:
  - `i = 0`, `ch = 'a'`: decrement count. `counts = {'a': 0, 'b': 1}`.
  - `i = 1`, `ch = 'a'`: 'a' count is 0, meaning we don't have enough 'a's left. Return `false`.

## Performance Analysis
- **Time Complexity:** $O(M + N)$ where $M$ is the length of `magazine` and $N$ is the length of `ransomNote`. We iterate through both strings once.
- **Space Complexity:** $O(1)$ because the `HashMap` or array will at most store the 26 lowercase English letters.
