---
name: "Ugly Number"
title: "LeetCode Ugly Number Solution"
description: "Solution for the ugly number problem from LeetCode."
published: "2021-07-13 PDT"
modified: "2021-07-13 PDT"
---

# Ugly Number Problem & Solution

An ugly number is a positive integer whose prime factors are limited to 2, 3, and 5.
Given an integer `n`, return true if `n` is an ugly number.

See the [ugly number problem on LeetCode](https://leetcode.com/problems/ugly-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isUgly(int n) {
    while (n > 1 && n % 2 == 0) {
      n /= 2;
    }

    while (n > 1 && n % 3 == 0) {
      n /= 3;
    }

    while (n > 1 && n % 5 == 0) {
      n /= 5;
    }

    return n == 1;
  }
};
```
