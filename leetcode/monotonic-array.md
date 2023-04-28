---
name: "Monotonic Array"
title: "LeetCode Monotonic Array Solution"
description: "Solution for an array is monotonic if it is either monotone increasing or monotone decreasing. An array nums is monotone increasing if for all i <= j, nums[i] <= nums[j]. An array nums is monotone decreasing if for all i <= j, nums[i] >= nums[j]. Given an integer array nums, return true if the given array is monotonic, or false otherwise."
published: "2021-12-12 PDT"
modified: "2021-12-12 PDT"
---

# Monotonic Array Problem & Solution

An array is monotonic if it is either monotone increasing or monotone decreasing.

An array `nums` is monotone increasing if for all `i <= j`, `nums[i] <= nums[j]`.
An array `nums` is monotone decreasing if for all `i <= j`, `nums[i] >= nums[j]`.

Given an integer array `nums`, return `true` if the given array is monotonic, or `false` otherwise.

See the [monotonic array problem on LeetCode](https://leetcode.com/problems/monotonic-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isMonotonic(vector<int>& nums) {
    bool increasing = true;
    bool decreasing = true;
    for (int i = 1; i < nums.size(); ++i) {
      increasing &= nums[i - 1] <= nums[i];
      decreasing &= nums[i - 1] >= nums[i];
    }

    return increasing || decreasing;
  }
};
```
