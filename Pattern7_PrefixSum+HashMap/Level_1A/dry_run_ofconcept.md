Dry Run

Consider:

nums = [1, 2, 3]
k = 3

Initially:

map = {0=1}
prefix = 0
count = 0
num = 1
prefix = 1


prefix - k
= 1 - 3
= -2

-2 isn't in map.

Store:

map = {0=1, 1=1}
num = 2
prefix = 3


prefix - k
= 3 - 3
= 0

0 exists!

Therefore:

count = 1

The subarray is:

[1,2]

Store:

map = {0=1, 1=1, 3=1}
num = 3
prefix = 6


prefix - k
= 6 - 3
= 3

3 exists.

Therefore:

count = 2

The second subarray is:

[3]

Answer:

2