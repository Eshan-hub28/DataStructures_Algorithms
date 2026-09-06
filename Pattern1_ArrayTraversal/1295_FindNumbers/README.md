# 1295. Find Numbers with Even Number of Digits

## Algorithm Explanation
The algorithm iterates through the given array of integers (`nums`) and counts how many of those integers contain an even number of digits. For each number, it determines the number of digits by repeatedly dividing the number by 10 in a `while` loop until it reaches 0. If the calculated number of digits is even (i.e., `digits % 2 == 0`), it increments the overall counter.

## Realistic Example (Input / Output)
**Input**: `nums = [12, 345, 2, 6, 7896]`
**Output**: `2`
*(Explanation: `12` has 2 digits (even), `345` has 3 (odd), `2` has 1 (odd), `6` has 1 (odd), `7896` has 4 (even). Therefore, exactly 2 numbers have an even number of digits.)*

## Step-by-Step Dry Run
Let's see how the algorithm processes the input `nums = [12, 345]`:

- **Initialization**: `count = 0`

- **Processing 1st number (`num = 12`)**: 
  - `temp = 12`, `digits = 0`
  - While loop:
    - `temp = 12 > 0`. `digits` becomes 1, `temp` becomes 1 (12 / 10).
    - `temp = 1 > 0`. `digits` becomes 2, `temp` becomes 0 (1 / 10).
  - Loop ends. Total digits = 2.
  - Is `2 % 2 == 0`? Yes. `count` becomes `1`.

- **Processing 2nd number (`num = 345`)**: 
  - `temp = 345`, `digits = 0`
  - While loop:
    - `temp = 345 > 0`. `digits` becomes 1, `temp` becomes 34.
    - `temp = 34 > 0`. `digits` becomes 2, `temp` becomes 3.
    - `temp = 3 > 0`. `digits` becomes 3, `temp` becomes 0.
  - Loop ends. Total digits = 3.
  - Is `3 % 2 == 0`? No. `count` remains `1`.

- **Final Step**: 
  - Return `count`, which is `1`.

## Performance Analysis
- **Time Complexity:** $O(N \cdot K)$, where $N$ is the length of the array and $K$ is the maximum number of digits in an element (at most 5 since LeetCode integers usually fit in standard bounds, so effectively $O(N)$).
- **Space Complexity:** $O(1)$, as we only use a few integer variables (`count`, `temp`, `digits`) regardless of the array size.
