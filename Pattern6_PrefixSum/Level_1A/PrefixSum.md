Pattern 3: Prefix Sum (Running Sum)
Problem without Prefix Sum

Suppose:

int[] nums = {2,4,6,8,10};

Question:

Find sum from index 1 to 3.

Meaning:

4 + 6 + 8

Answer:

18

Simple approach:

int sum = 0;

for(int i = 1; i <= 3; i++){
    sum += nums[i];
}

This works.

But imagine:

Find sum from index 100 to 500
Find sum from index 200 to 700
Find sum from index 50 to 900

Doing loops again and again is slow.

Prefix Sum Idea

We create a new array that stores the running total.

Original array:

nums:

index:
0  1  2  3  4

2  4  6  8 10

Create prefix:

prefix:

index:
0  1  2  3  4

2  6 12 20 30

Meaning:

prefix[0] = nums[0]

prefix[1] = nums[0]+nums[1]

prefix[2] = nums[0]+nums[1]+nums[2]
Template 1: Building Prefix Sum
Syntax
int[] prefix = new int[nums.length];

prefix[0] = nums[0];

for(int i = 1; i < nums.length; i++){

    prefix[i] = prefix[i-1] + nums[i];

}
How this runs

Example:

nums = {2,4,6,8,10}

Create:

int[] prefix = new int[5];

Initially:

prefix:

0 0 0 0 0
Step 1
prefix[0] = nums[0];

nums[0]:

2

prefix:

2 0 0 0 0
Step 2

i = 1

prefix[1] = prefix[0] + nums[1];

Substitute:

prefix[1] = 2 + 4

Result:

6

prefix:

2 6 0 0 0
Step 3

i = 2

prefix[2] = prefix[1] + nums[2];
6 + 6

= 12

prefix:

2 6 12 0 0
Step 4

i = 3

12 + 8 = 20

prefix:

2 6 12 20 0
Step 5

i = 4

20 + 10 = 30

Final:

prefix:

2 6 12 20 30
Template 2: Find Range Sum

Now we have prefix.

Question:

Find sum from index left to right.

Formula:

sum(left,right)

=
prefix[right] - prefix[left-1]

Example:

nums:

2 4 6 8 10


prefix:

2 6 12 20 30

Find:

index 1 to 3

Meaning:

4+6+8

We use:

prefix[3] - prefix[0]

Why?

prefix[3]
=
2+4+6+8

20


prefix[0]
=
2

Remove unwanted part:

20 - 2

=18

Answer:

18
Code
int rangeSum(int[] prefix, int left, int right){

    if(left == 0){
        return prefix[right];
    }

    return prefix[right] - prefix[left-1];
}