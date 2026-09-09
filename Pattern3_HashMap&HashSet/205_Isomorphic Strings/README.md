# 205. Isomorphic Strings

## Algorithm Explanation
The algorithm determines if two strings `s` and `t` are isomorphic by checking if the characters in `s` can be replaced to get `t`. 
It uses two `HashMap`s (or dictionaries) to keep track of the character mappings from `s` to `t` and from `t` to `s`. As we iterate through the strings, we check if a character in `s` is already mapped to a different character in `t`, or if a character in `t` is already mapped to a different character in `s`. If either condition is true, we return `false`. If we finish the loop without any mapping conflicts, the strings are isomorphic and we return `true`.

## Realistic Example (Input / Output)
**Input**: `s = "egg"`, `t = "add"`
**Output**: `true`
*(Explanation: 'e' maps to 'a', and 'g' maps to 'd'. Both mappings are consistent.)*

## Step-by-Step Dry Run
Let's trace the input `s = "egg", t = "add"`:
- **Step 1 (First characters)**:
  - `i = 0`: `ch1 = 'e'`, `ch2 = 'a'`. Both maps are empty. Add mapping `map1 = {'e': 'a'}`, `map2 = {'a': 'e'}`.
- **Step 2 (Second characters)**:
  - `i = 1`: `ch1 = 'g'`, `ch2 = 'd'`. Not in map. Add mapping `map1 = {'e': 'a', 'g': 'd'}`, `map2 = {'a': 'e', 'd': 'g'}`.
- **Step 3 (Third characters)**:
  - `i = 2`: `ch1 = 'g'`, `ch2 = 'd'`. `ch1` is in `map1` and maps to `'d'`, which matches `ch2`. `ch2` is in `map2` and maps to `'g'`, which matches `ch1`.
- **Final Step**: 
  - Loop finishes without conflicts, return `true`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the length of the string. We iterate through the strings once, and hash map lookups are $O(1)$.
- **Space Complexity:** $O(1)$ or $O(K)$ where $K$ is the number of unique characters. Since there are at most 256 valid ASCII characters, the space is limited to $O(1)$ constant space.
