# 2011. Final Value of Variable After Performing Operations

## Algorithm Explanation
*(Note: There is a bug in the current code implementation, but we will explain and trace exactly what the written code performs).*
The code attempts to process an array of operation strings (`operations`). For each `sentence` (operation) in the array, it initializes an inner loop that iterates over each character in the string `sentence` (`sentence.length()` times). Inside this character loop, it looks purely at the second character of the string (`sentence.charAt(1)`). If it is `'+'`, it increments `count`. If it is `'-'`, it decrements `count`. Because the inner loop iterates for *every* character in the string, it repeats the update `sentence.length()` times for each operation.

## Realistic Example (Input / Output based on the written code)
**Input**: `operations = ["--X", "X++", "X++"]`
**Output**: `3`
*(Explanation of bug: For "--X", length is 3. `charAt(1)` is `-`. It decrements 3 times (-3). For "X++", length is 3. `charAt(1)` is `+`. It increments 3 times (+3). The next "X++" adds another 3. Total: -3 + 3 + 3 = 3. Expected answer for LC was 1, but this code produces 3.)*

## Step-by-Step Dry Run (Actual Code Behavior)
Let's see how the algorithm processes `operations = ["--X", "X++"]`:

- **Initialization**: `count = 0`

- **Processing 1st operation (`sentence = "--X"`)**: 
  - String length is 3. The inner loop will run for `i = 0, 1, 2`.
  - `i = 0`: `sentence.charAt(1)` is `'-'`. `count` becomes `-1`.
  - `i = 1`: `sentence.charAt(1)` is `'-'`. `count` becomes `-2`.
  - `i = 2`: `sentence.charAt(1)` is `'-'`. `count` becomes `-3`.

- **Processing 2nd operation (`sentence = "X++"`)**: 
  - String length is 3. The inner loop will run for `i = 0, 1, 2`.
  - `i = 0`: `sentence.charAt(1)` is `'+'`. `count` becomes `-2`.
  - `i = 1`: `sentence.charAt(1)` is `'+'`. `count` becomes `-1`.
  - `i = 2`: `sentence.charAt(1)` is `'+'`. `count` becomes `0`.

- **Final Step**: 
  - Returns `count`, which is `0`. (Whereas the true value would be 0 mathematically if each operation ran once).

## Performance Analysis
- **Time Complexity:** $O(N \times L)$, where $N$ is the number of operations and $L$ is the length of each string (which is 3 in this problem). So effectively $O(N)$.
- **Space Complexity:** $O(1)$, as we only keep track of a single `count` variable.
