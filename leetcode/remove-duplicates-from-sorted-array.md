---
name: "Remove Duplicates from Sorted Array"
title: "LeetCode Remove Duplicates from Sorted Array Solution"
description: "Solution for the remove duplicates from sorted array problem from LeetCode."
published: "2021-05-16 PDT"
modified: "2021-06-09 PDT"
---

# Remove Duplicates from Sorted Array Problem & Solution

Given a sorted array `nums`, remove the duplicates in-place such that each element appears only once and returns the new length.

See the [remove duplicates from sorted array problem on LeetCode](https://leetcode.com/problems/remove-duplicates-from-sorted-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int removeDuplicates(vector<int>& nums) {
    if (nums.size() == 0) {
      return 0;
    }

    int j = 0;

    for (int i = 1; i < nums.size(); ++i) {
      if (nums[j] != nums[i]) {
        nums[++j] = nums[i];
      }
    }

    return j + 1;
  }
};
```
