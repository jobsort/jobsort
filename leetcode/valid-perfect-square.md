---
name: "Valid Perfect Square"
title: "LeetCode Valid Perfect Square Solution"
description: "Solution for the valid perfect square problem from LeetCode."
published: "2021-07-03 PDT"
modified: "2021-07-03 PDT"
---

# Valid Perfect Square Problem & Solution

Given a positive integer `num`, write a function which returns True if `num` is a perfect square else False.
Do not use any built-in library function such as `sqrt`.

See the [valid perfect square problem on LeetCode](https://leetcode.com/problems/valid-perfect-square).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isPerfectSquare(int num) {
    int low = 0;
    int high = num;
    while (low < high) {
      int mid = low + (high - low) / 2;

      // Avoids computing `mid * mid < num` because it overflows.
      if (mid == 0 || mid < num / mid) {
        low = mid + 1;
      } else {
        high = mid;
      }
    }

    // Must do a float comparison rather than int to avoid rounding errors.
    return low != 0 && low == (float)num / low;
  }
};
```
