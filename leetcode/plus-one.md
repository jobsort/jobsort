---
name: "Plus One"
title: "LeetCode Plus One Solution"
description: "Solution for the plus one problem from LeetCode."
published: "2021-05-29 PDT"
modified: "2021-06-09 PDT"
---

# Plus One Problem & Solution

Given a non-empty array of decimal digits representing a non-negative integer, increment one to the integer.

See the [plus one problem on LeetCode](https://leetcode.com/problems/plus-one).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> plusOne(vector<int>& digits) {
    int carryover = 1;

    for (int i = digits.size() - 1; i >= 0; --i) {
      digits[i] += carryover;
      carryover = digits[i] / 10;
      digits[i] %= 10;
    }

    if (carryover > 0) {
      digits.insert(digits.begin(), carryover);
    }

    return digits;
  }
};
```
