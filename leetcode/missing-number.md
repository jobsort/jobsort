---
name: "Missing Number"
title: "LeetCode Missing Number Solution"
description: "Solution for given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array."
published: "2021-07-13 PDT"
modified: "2021-08-01 PDT"
---

# Missing Number Problem & Solution

Given an array nums containing `n` distinct numbers in the range `[0, n]`, return the only number in the range that is missing from the array.

See the [missing number problem on LeetCode](https://leetcode.com/problems/missing-number).

## C++ Solution

The runtime complexity of this algorithm is $O(n)$.

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int missingNumber(vector<int>& nums) {
    int sum = nums.size();
    for (int i = 0; i < nums.size(); ++i) {
      sum += i;
      sum -= nums[i];
    }

    return sum;
  }
};
```
