---
name: "Largest Perimeter Triangle"
title: "LeetCode Largest Perimeter Triangle Solution"
description: "Solution for given an integer array nums, return the largest perimeter of a triangle with a non-zero area, formed from three of these lengths. If it is impossible to form any triangle of a non-zero area, return 0."
published: "2021-12-10 PDT"
modified: "2021-12-10 PDT"
---

# Largest Perimeter Triangle Problem & Solution

Given an integer array `nums`, return the largest perimeter of a triangle with a non-zero area, formed from three of these lengths.
If it is impossible to form any triangle of a non-zero area, return `0`.

See the [largest perimeter triangle problem on LeetCode](https://leetcode.com/problems/largest-perimeter-triangle).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int largestPerimeter(vector<int>& nums) {
    sort(nums.begin(), nums.end(), greater<>());
    for (int i = 2; i < nums.size(); ++i) {

      // https://en.wikipedia.org/wiki/Triangle_inequality
      if (nums[i - 2] < nums[i - 1] + nums[i]) {
        return nums[i - 2] + nums[i - 1] + nums[i];
      }
    }

    return 0;
  }
};
```
