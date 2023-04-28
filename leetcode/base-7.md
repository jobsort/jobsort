---
name: "Base 7"
title: "LeetCode Base 7 Solution"
description: "Solution for given an integer num, return a string of its base 7 representation."
published: "2021-08-07 PDT"
modified: "2021-08-07 PDT"
---

# Base 7 Problem & Solution

Given an integer `num`, return a string of its base 7 representation.

See the [base 7 problem on LeetCode](https://leetcode.com/problems/base-7).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string convertToBase7(int num) {
    int positive = abs(num);

    string result;
    while (positive > 0) {
      result += positive % 7 + '0';
      positive /= 7;
    }

    if (num < 0) {
      result += '-';
    } else if (num == 0) {
      result = "0";
    }

    reverse(result.begin(), result.end());

    return result;
  }
};
```
