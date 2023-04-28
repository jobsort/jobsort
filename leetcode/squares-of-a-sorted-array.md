---
name: "Squares of a Sorted Array"
title: "LeetCode Squares of a Sorted Array Solution"
description: "Solution for given an integer array nums sorted in non-decreasing order, return an array of the squares of each number sorted in non-decreasing order."
published: "2021-12-11 PDT"
modified: "2021-12-11 PDT"
---

# Squares of a Sorted Array Problem & Solution

Given an integer array nums sorted in non-decreasing order, return an array of the squares of each number sorted in non-decreasing order.

See the [squares of a sorted array problem on LeetCode](https://leetcode.com/problems/squares-of-a-sorted-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> sortedSquares(vector<int>& nums) {
    int p = 0;
    while (p < nums.size() && nums[p] < 0) {
      ++p;
    }

    int n = p - 1;

    vector<int> result;
    while (n >= 0 && p < nums.size()) {
      if (abs(nums[n]) < nums[p]) {
        result.push_back(pow(nums[n], 2));
        --n;
      } else {
        result.push_back(pow(nums[p], 2));
        ++p;
      }
    }

    while (n >= 0) {
      result.push_back(pow(nums[n], 2));
      --n;
    }

    while (p < nums.size()) {
      result.push_back(pow(nums[p], 2));
      ++p;
    }

    return result;
  }
};
```
