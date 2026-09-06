# 2114. Maximum Number of Words Found in Sentences

## Algorithm Explanation
The algorithm finds the maximum number of words across an array of `sentences`. It iterates through each string (`sentence`) in the array. For each sentence, it assumes there is at least `1` word. Then, it iterates through every character of the sentence. Whenever it encounters a space character (`' '`), it increments the `words` counter by 1. After processing the characters of a sentence, it updates the global maximum (`maxi`) by comparing it with the number of words in the current sentence. Finally, it returns `maxi`.

## Realistic Example (Input / Output)
**Input**: `sentences = ["alice and bob love leetcode", "i think so too"]`
**Output**: `5`
*(Explanation: First sentence has 4 spaces -> 5 words. Second has 3 spaces -> 4 words. Max is 5.)*

## Step-by-Step Dry Run
Let's see how the algorithm processes `sentences = ["a b", "i think so"]`:

- **Initialization**: `maxi = 0`

- **Processing 1st sentence (`sentence = "a b"`)**: 
  - `words = 1`
  - Loop `i` from 0 to 2 (`"a b".length() = 3`):
    - `i = 0` ('a'): Not a space.
    - `i = 1` (' '): It's a space! `words++` (becomes 2).
    - `i = 2` ('b'): Not a space.
  - `maxi = max(2, 0) = 2`

- **Processing 2nd sentence (`sentence = "i think so"`)**: 
  - `words = 1`
  - Loop `i` from 0 to 9 (`"i think so".length() = 10`):
    - `i = 0` ('i'): Not space.
    - `i = 1` (' '): Space! `words++` (becomes 2).
    - `i = 2` to `i = 6` ('think'): Not spaces.
    - `i = 7` (' '): Space! `words++` (becomes 3).
    - `i = 8` to `i = 9` ('so'): Not spaces.
  - `maxi = max(3, 2) = 3`

- **Final Step**: 
  - Return `maxi`, which is `3`.

## Performance Analysis
- **Time Complexity:** $O(C)$ where $C$ is the total number of characters across all sentences in the array. The algorithm examines every single character exactly once.
- **Space Complexity:** $O(1)$ since only a few integer variables (`maxi`, `words`, `i`) are used.
