---
name: "Move Zeroes"
title: "LeetCode Move Zeroes Solution"
description: "Solution for the move zeroes problem from LeetCode."
published: "2021-07-12 PDT"
modified: "2021-07-12 PDT"
---

# Move Zeroes Problem & Solution

Given an integer array `nums`, move all 0's to the end of it while maintaining the relative order of the non-zero elements.
Note that you must do this in-place without making a copy of the array.

See the [move zeroes problem on LeetCode](https://leetcode.com/problems/move-zeroes).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  void moveZeroes(vector<int>& nums) {
    for (int i = 0; i < nums.size(); ++i) {
      if (nums[i] == 0) {
        int j = i + 1;

        // Skips consecutive zeroes.
        while (j < nums.size() && nums[j] == 0) {
          ++j;
        }

        rotate(nums.begin() + i, nums.begin() + j, nums.end());
      }
    }
  }
};
```
