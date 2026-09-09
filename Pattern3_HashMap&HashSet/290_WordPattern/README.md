# 290. Word Pattern

## Algorithm Explanation
The algorithm determines if a string `s` follows a given `pattern`. 
First, the string `s` is split into individual words. If the number of characters in `pattern` does not match the number of words in `s`, we return `false`. We then use two `HashMap`s to establish a bidirectional mapping between the characters in `pattern` and the words in `s`. If a character is already mapped to a different word, or if a word is already mapped to a different character, the pattern is invalid. Otherwise, we record the mappings.

## Realistic Example (Input / Output)
**Input**: `pattern = "abba"`, `s = "dog cat cat dog"`
**Output**: `true`
*(Explanation: 'a' maps to "dog" and 'b' maps to "cat". The mappings are consistent in both directions.)*

## Step-by-Step Dry Run
Let's trace `pattern = "abba"`, `s = "dog cat cat dog"`:
- **Split**: `words = ["dog", "cat", "cat", "dog"]`. Lengths match (4 = 4).
- **Step 1**: `char = 'a'`, `word = "dog"`. Add to both maps. `charToWord = {'a': "dog"}`, `wordToChar = {"dog": 'a'}`.
- **Step 2**: `char = 'b'`, `word = "cat"`. Add to both maps. `charToWord = {'a': "dog", 'b': "cat"}`, `wordToChar = {"dog": 'a', "cat": 'b'}`.
- **Step 3**: `char = 'b'`, `word = "cat"`. Matches existing mapping.
- **Step 4**: `char = 'a'`, `word = "dog"`. Matches existing mapping.
- **Final Step**: Loop finishes, return `true`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the length of `pattern` (or string `s`). Splitting the string and iterating through the words both take linear time.
- **Space Complexity:** $O(N)$ to store the words array and the HashMaps.
