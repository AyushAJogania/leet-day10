# Implement pow(x, n) - LeetCode Problem

## Problem Description

You are given a double `x` and an integer `n`. Your task is to calculate `x` raised to the power `n` (i.e., `x^n`).

### Example 1:

Input: `x = 2.00000`, `n = 10`
Output: `1024.00000`

### Example 2:

Input: `x = 2.10000`, `n = 3`
Output: `9.26100`

### Example 3:

Input: `x = 2.00000`, `n = -2`
Output: `0.25000`
Explanation: `2^-2 = 1/(2^2) = 1/4 = 0.25`

## Constraints:

- `-100.0 < x < 100.0`
- `-2^31 <= n <= 2^31-1`
- `n` is an integer.
- Either `x` is not zero or `n > 0`.
- `-10^4 <= x^n <= 10^4`

## Approach

To efficiently calculate `x^n`, we can use the following recursive approach:

1. Base case: If `n` is 0, return 1.0 (anything raised to the power 0 is 1).
2. If `n` is 1, return `x` (anything raised to the power 1 is itself).
3. If `n` is -1, return `1.0 / x` (handling negative exponent case).
4. Calculate `half = pow(x, n / 2)` and `rem = pow(x, n % 2)`.
5. Return `half * half * rem`.

This approach reduces the number of multiplications required, making it more efficient for larger values of `n`.

## Complexity Analysis

The time complexity of this approach is O(log n) because the input `n` is halved at each recursive call, leading to a binary tree-like recursion pattern.

The space complexity is O(log n) due to the recursion stack used to calculate the result.

## Summary

The `myPow` function efficiently calculates `x` raised to the power `n` using a recursive approach. It handles both positive and negative exponents and provides an efficient solution for the problem.
