---
name: "Majority Element"
title: "LeetCode Majority Element Solution"
description: "Solution for the majority element problem from LeetCode."
published: "2021-06-15 PDT"
modified: "2021-06-15 PDT"
---

# Majority Element Problem & Solution

Given an array `nums` of size `n`, return the majority element.

The majority element is the element that appears more than `⌊n / 2⌋` times.
You may assume that the majority element always exists in the array.

See the [majority element problem on LeetCode](https://leetcode.com/problems/majority-element).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int majorityElement(vector<int>& nums) {
    int candidate = 0;
    int count = 0;

    for (int i = 0; i < nums.size(); ++i) {
      if (count == 0) {
        candidate = nums[i];
      }

      count += nums[i] == candidate ? 1 : -1;
    }

    return candidate;
  }
};
```
