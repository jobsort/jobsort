---
name: "Two Sum II"
title: "LeetCode Two Sum II Solution"
description: "Solution for the two sum ii problem from LeetCode."
published: "2021-06-22 PDT"
modified: "2021-06-22 PDT"
---

# Two Sum II Problem & Solution

Given an array of integers `numbers` that is already sorted in non-decreasing order, find two numbers such that they add up to a specific `target` number.

See the [two sum ii problem on LeetCode](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> twoSum(vector<int>& numbers, int target) {
    int i = 0;
    int j = numbers.size() - 1;

    while (i < j) {
      if (numbers[i] + numbers[j] == target) {
        return {i + 1, j + 1};
      } else if (numbers[i] + numbers[j] < target) {
        ++i;
      } else {
        --j;
      }
    }

    return {1, 2};
  }
};
```
