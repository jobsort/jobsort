---
name: "Single Number"
title: "LeetCode Single Number Solution"
description: "Solution for the single number problem from LeetCode."
published: "2021-06-10 PDT"
modified: "2021-06-10 PDT"
---

# Single Number Problem & Solution

Given a non-empty array of integers `nums`, every element appears twice except for one.
Find that single one.
You must implement a solution with a linear runtime complexity and use only constant extra space.

See the [single number problem on LeetCode](https://leetcode.com/problems/single-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int singleNumber(vector<int>& nums) {
    int result = 0;

    for (int i = 0; i < nums.size(); ++i) {

      // Performs a XOR to cancel out numbers that repeat again.
      result ^= nums[i];
    }

    return result;
  }
};
```
