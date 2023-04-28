---
name: "Number of 1 Bits"
title: "LeetCode Number of 1 Bits Solution"
description: "Solution for the number of 1 bits problem from LeetCode."
published: "2021-06-24 PDT"
modified: "2021-06-24 PDT"
---

# Number of 1 Bits Problem & Solution

Write a function that takes an unsigned integer and returns the number of '1' bits it has (also known as the Hamming weight).

See the [number of 1 bits problem on LeetCode](https://leetcode.com/problems/number-of-1-bits).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int hammingWeight(uint32_t n) {
    return  __builtin_popcount(n);
  }
};
```
