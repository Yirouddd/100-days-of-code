# Divide and Conquer

## [312] Burst Balloons

**Difficulty**: ⭐️⭐️⭐️ Hard  
**Date**: 2026-03-07  
**Tags**: `Divide and Conquer`, `Dynamic Programming`

### Problem Description

You are given `n` balloons, indexed from `0` to `n - 1`. Each balloon is painted with a number on it represented by an array `nums`. You are asked to burst all the balloons.  

If you burst the `i`-th balloon, you will get `nums[i - 1] * nums[i] * nums[i + 1]` coins. If `i - 1` or `i + 1` goes out of bounds of the array, then treat it as if there is a balloon with a `1` painted on it.  

Return the maximum coins you can collect by bursting the balloons wisely.  

### Core Idea

#### Reverse Thinking 🔄

Don't think about "which one to burst first," but rather **"which one to burst last."**

**Why?**
- **Forward approach**: Popping a balloon changes the array, making neighbor relationships difficult to handle.
- **Reverse approach**: The left and right neighbors of the balloon that is popped last are fixed (values outside the interval).

#### Interval Dynamic Programming

Define `dp[i][j]` = maximum coins obtained by bursting all balloons from index `i` to `j`.

**State Transition**: dp[i][j] = max(dp[i][k-1] + dp[k+1][j] + nums[i-1] * nums[k] * nums[j+1]) for k in [i, j]  

Where `k` is the **last balloon** to be burst in the current interval.
**Note**: Add `1` at both ends of the original array to handle boundary cases easily.

### Pseudocode

```cpp  
n = nums.length
// Add virtual boundaries
newNums = [1] + nums + [1]
dp = 2D array of size [n+2][n+2] initialized to 0

// Interval length from 1 to n
for length = 1 to n:
    for i = 1 to n - length + 1:
        j = i + length - 1
        // Try each k as the last balloon to burst
        for k = i to j:
            coins = dp[i][k-1] + dp[k+1][j] 
                    + newNums[i-1] * newNums[k] * newNums[j+1]
            dp[i][j] = max(dp[i][j], coins)

return dp[1][n]
```

### Common Pitfalls ⚠️

#### 1. Subinterval vs Entire Interval
- **Entire interval last burst**: Left and right neighbors are virtual `1`s.
- **Subinterval last burst**: Left and right neighbors are values outside the subinterval (could be actual array numbers).

#### 2. Index Handling
- Original array indices: `0` to `n-1` → After adding boundaries: `1` to `n`
- `points[i-1]` and `points[j+1]` represent the left and right neighbors

#### 3. Traversal Order
- Must calculate smaller intervals first, then larger intervals
- Reason: Larger intervals depend on the results of smaller intervals

#### 4. Initialization
- `dp[i][j]` starts at `0`
- Empty intervals (where `i > j`) require no bursting, so they contribute `0` coins

### Time & Space Complexity

- **Time Complexity**: O(n³) — triple nested loops
- **Space Complexity**: O(n²) — for the DP table
