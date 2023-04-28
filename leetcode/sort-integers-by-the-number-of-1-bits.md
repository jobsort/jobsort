---
name: "Sort Integers by the Number of 1 Bits"
title: "LeetCode Sort Integers by the Number of 1 Bits Solution"
description: "Solution for the sort integers by the number of 1 bits problem from LeetCode."
published: "2022-03-26 PDT"
modified: "2022-03-26 PDT"
---

# Sort Integers by the Number of 1 Bits Problem & Solution

See the [sort integers by the number of 1 bits problem on LeetCode](https://leetcode.com/problems/sort-integers-by-the-number-of-1-bits).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> sortByBits(vector<int>& arr) {
    sort(arr.begin(), arr.end(), [](int a, int b) {
      int abits = __builtin_popcount(a);
      int bbits = __builtin_popcount(b);
      if (abits < bbits) {
        return true;
      } else if (abits > bbits) {
        return false;
      } else {
        return a < b;
      }
    });

    return arr;
  }
};
```
