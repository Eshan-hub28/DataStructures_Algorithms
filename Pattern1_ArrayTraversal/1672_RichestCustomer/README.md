# 1672. Richest Customer Wealth

## Algorithm Explanation
The algorithm determines the wealth of the richest customer. It iterates through an `accounts` 2D array, where each row represents a customer and each column represents a bank account. For each customer, it calculates their total wealth by summing up all the money across their bank accounts. It keeps track of the maximum wealth found so far (`maxwealth`) and returns it at the end.

## Realistic Example (Input / Output)
**Input**: `accounts = [[1, 2, 3], [3, 2, 1]]`
**Output**: `6`
*(Explanation: Customer 1 has 1+2+3=6. Customer 2 has 3+2+1=6. Both have 6, so max wealth is 6.)*

## Step-by-Step Dry Run
Let's see how the algorithm processes the input `accounts = [[1, 2, 3], [3, 2, 1]]`:

- **Initialization**: `maxwealth = 0`

- **Processing Customer 0 (`i = 0`, `accounts[0] = [1, 2, 3]`)**: 
  - `wealth = 0`
  - Inner loop (`j = 0`): `wealth += accounts[0][0]` (1). `wealth = 1`.
  - Inner loop (`j = 1`): `wealth += accounts[0][1]` (2). `wealth = 3`.
  - Inner loop (`j = 2`): `wealth += accounts[0][2]` (3). `wealth = 6`.
  - `maxwealth = max(6, 0) = 6`

- **Processing Customer 1 (`i = 1`, `accounts[1] = [3, 2, 1]`)**: 
  - `wealth = 0`
  - Inner loop (`j = 0`): `wealth += accounts[1][0]` (3). `wealth = 3`.
  - Inner loop (`j = 1`): `wealth += accounts[1][1]` (2). `wealth = 5`.
  - Inner loop (`j = 2`): `wealth += accounts[1][2]` (1). `wealth = 6`.
  - `maxwealth = max(6, 6) = 6`

- **Final Step**: 
  - Loop ends since `i` reaches 2. Return `maxwealth` which is `6`.

## Performance Analysis
- **Time Complexity:** $O(M \times N)$ where $M$ is the number of customers (rows) and $N$ is the number of bank accounts (columns). Every cell is visited once.
- **Space Complexity:** $O(1)$, as we only use two integer variables (`maxwealth` and `wealth`).
