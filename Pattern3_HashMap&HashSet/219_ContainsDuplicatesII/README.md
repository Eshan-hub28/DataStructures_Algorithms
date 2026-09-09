# 219. Contains Duplicate II (HashSet Sliding Window Approach)

## Algorithm Explanation
The algorithm checks if there are two duplicate elements in the array `nums` such that their indices are at most `k` apart.
It uses a `HashSet` to maintain a "sliding window" of the most recent `k` elements. As we iterate through the array, we check if the current element is already in the `HashSet`. If it is, we return `true` since the window size ensures the distance is $\le k$. Then we add the current element to the set. If the size of the set exceeds `k`, we remove the oldest element (at index `i - k`) from the set to maintain the sliding window property.

## Realistic Example (Input / Output)
**Input**: `nums = [1, 2, 3, 1]`, `k = 3`
**Output**: `true`
*(Explanation: The element `1` appears at index 0 and index 3, and the difference between indices is 3 $\le$ 3.)*

## Step-by-Step Dry Run
Let's trace the input `nums = [1, 2, 3, 1]`, `k = 3`:
- **Step 1**: `i = 0`, `nums[0] = 1`. Set is empty, add `1`. `set = {1}`. Set size $\le 3$.
- **Step 2**: `i = 1`, `nums[1] = 2`. `2` not in set, add `2`. `set = {1, 2}`. Set size $\le 3$.
- **Step 3**: `i = 2`, `nums[2] = 3`. `3` not in set, add `3`. `set = {1, 2, 3}`. Set size $\le 3$.
- **Step 4**: `i = 3`, `nums[3] = 1`. `1` is already in the set! We return `true`.

## Performance Analysis
- **Time Complexity:** $O(N)$ where $N$ is the number of elements in the array. We process each element once, and `HashSet` operations are $O(1)$.
- **Space Complexity:** $O(\min(N, k))$ as the `HashSet` stores at most $k$ elements at any given time to represent the sliding window.
