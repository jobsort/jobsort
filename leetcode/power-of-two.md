---
name: "Power of Two"
title: "LeetCode Power of Two Solution"
description: "Solution for the power of two problem from LeetCode."
published: "2021-06-29 PDT"
modified: "2021-06-29 PDT"
---

# Power of Two Problem & Solution

Given an integer `n`, return true if it is a power of two.
Otherwise, return false.
An integer `n` is a power of two, if there exists an integer `x` such that `n == 2^x`.

See the [power of two problem on LeetCode](https://leetcode.com/problems/power-of-two).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isPowerOfTwo(int n) {
    if (n <= 0) {
      return false;
    }

    return pow(2, (int)log2(n)) == n;
  }
};
```
