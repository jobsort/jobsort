---
name: "Array Partition I"
title: "LeetCode Array Partition I Solution"
description: "Solution for the array partition i problem from LeetCode."
published: "2021-07-21 PDT"
modified: "2021-07-21 PDT"
---

# Array Partition I Problem & Solution

Given an integer array `nums` of 2n integers, group these integers into n pairs (a1, b1), (a2, b2), ..., (an, bn) such that the sum of min(ai, bi) for all i is maximized.
Return the maximized sum.

See the [array partition i problem on LeetCode](https://leetcode.com/problems/array-partition-i).

## C++ Solution

The runtime complexity of this algorithm is $O(n\log{}n)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int arrayPairSum(vector<int>& nums) {
    sort(nums.begin(), nums.end());

    int sum = 0;
    for (int i = 0; i < nums.size(); i += 2) {
      sum += min(nums[i], nums[i + 1]);
    }

    return sum;
  }
};
```
