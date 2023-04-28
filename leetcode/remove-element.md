---
name: "Remove Element"
title: "LeetCode Remove Element Solution"
description: "Solution for the remove element problem from LeetCode."
published: "2021-05-16 PDT"
modified: "2021-06-09 PDT"
---

# Remove Element Problem & Solution

Given an array `nums` and a value `val`, remove all instances of that value in-place and return the new length.

See the [remove element problem on LeetCode](https://leetcode.com/problems/remove-element).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int removeElement(vector<int>& nums, int val) {
    int j = 0;

    for (int i = 0; i < nums.size(); ++i) {
      if (nums[i] != val) {
        nums[j++] = nums[i];
      }
    }

    return j;
  }
};
```
