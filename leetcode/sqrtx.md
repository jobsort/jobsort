---
name: "sqrt(x)"
title: "LeetCode sqrt(x) Solution"
description: "Solution for the sqrt(x) problem from LeetCode."
published: "2021-06-01 PDT"
modified: "2021-06-09 PDT"
---

# sqrt(x) Problem & Solution

Given a non-negative integer `x`, compute and return the square root of `x`.
Since the return type is an integer, the decimal digits are truncated, and only the integer part of the result is returned.

See the [sqrt(x) problem on LeetCode](https://leetcode.com/problems/sqrtx).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int mySqrt(int x) {
    int low = 0;
    int high = x;
    while (low < high) {
      int mid = low + (high - low) / 2;

      // Avoid overflow when computing `mid * mid < x`.
      if (mid == 0 || mid < x / mid) {
        low = mid + 1;
      } else {
        high = mid;
      }
    }

    // Avoids overflow when computing `low * low > x`.
    return low != 0 && low > x / low ? low - 1 : low;
  }
};
```
