---
name: "Third Maximum Number"
title: "LeetCode Third Maximum Number Solution"
description: "Solution for the third maximum number problem from LeetCode."
published: "2021-07-27 PDT"
modified: "2021-07-27 PDT"
---

# Third Maximum Number Problem & Solution

Given integer array `nums`, return the third maximum number in this array.
If the third maximum does not exist, return the maximum number.

See the [third maximum number problem on LeetCode](https://leetcode.com/problems/third-maximum-number).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int thirdMax(vector<int>& nums) {
    long max1 = LONG_MIN;
    for (int i = 0; i < nums.size(); ++i) {
      max1 = max(max1, (long)nums[i]);
    }

    long max2 = LONG_MIN;
    for (int i = 0; i < nums.size(); ++i) {
      if (nums[i] != max1) {
        max2 = max(max2, (long)nums[i]);
      }
    }

    long max3 = LONG_MIN;
    for (int i = 0; i < nums.size(); ++i) {
      if (nums[i] != max1 && nums[i] != max2) {
        max3 = max(max3, (long)nums[i]);
      }
    }

    return max3 != LONG_MIN ? max3 : max1;
  }
};
```
