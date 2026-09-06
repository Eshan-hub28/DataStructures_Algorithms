Why map.put(0, 1)?

This is very important.

Consider:

nums = [3]
k = 3

At the first element:

prefix = 3

We need:

prefix - k
= 3 - 3
= 0

So we need 0 to already exist in our map.

That's why:

map.put(0, 1);

means:

"Before processing any elements, we've seen a prefix sum of 0 once."

This allows us to detect subarrays that start from index 0.