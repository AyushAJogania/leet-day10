# leet-day10

# LeetCode Problem: Generate Parentheses (Problem #22)

## Problem Description

Given `n` pairs of parentheses, write a function to generate all combinations of well-formed parentheses.

## Example

Input: `n = 3`

Output: `["((()))","(()())","(())()","()(())","()()()"]`

## Constraints

- `1 <= n <= 8`

## Approach

To generate all combinations of well-formed parentheses, we can use backtracking. We start with an empty string and recursively build the combinations by adding open and close parentheses based on certain conditions.

1. Initialize an empty vector `result` to store the generated combinations.
2. Create a helper function `backtrack` that takes the current combination string `current`, the number of open parentheses `open`, the number of close parentheses `close`, and the total number of pairs `n`.
3. The base case for recursion is when the length of the current combination is equal to `2 * n`. At this point, we add the current combination to the `result` vector.
4. If the number of open parentheses (`open`) is less than `n`, we can add an open parenthesis to the current combination and call the `backtrack` function recursively with `open + 1`.
5. If the number of close parentheses (`close`) is less than `open`, we can add a close parenthesis to the current combination and call the `backtrack` function recursively with `close + 1`.
6. Finally, we call the `backtrack` function with the initial values of `current = ""`, `open = 0`, and `close = 0`.

## Complexity Analysis

The time complexity of the backtracking solution is O(2^(2n) * n) because for each position in the combination, we have two choices: open or close parenthesis, and we do this for a total of 2^(2n) positions. The number of elements in the result vector is bounded by the Catalan number Cn, which is approximately (4^n)/(n^(3/2)). Therefore, the space complexity of the solution is O(Cn * n) or O(4^n).

## Summary

The backtracking approach allows us to generate all combinations of well-formed parentheses efficiently. By using recursion and making decisions based on the number of open and close parentheses, we can explore all possible combinations and build the final result. The time and space complexity of the solution are reasonable for the given constraints.
