---
name: "Maximum Count of Positive Integer and Negative Integer"
title: "LeetCode Maximum Count of Positive Integer and Negative Integer Solution"
description: "Solution for the maximum count of positive integer and negative integer problem from LeetCode."
published: "2023-01-26 PDT"
modified: "2023-01-26 PDT"
---

# Maximum Count of Positive Integer and Negative Integer Problem & Solution

See the [maximum count of positive integer and negative integer problem on LeetCode](https://leetcode.com/problems/maximum-count-of-positive-integer-and-negative-integer).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int maximumCount(vector<int>& nums) {
    auto negit = upper_bound(nums.begin(), nums.end(), -1);
    auto posit = lower_bound(nums.begin(), nums.end(), 1);

    int neg = distance(nums.begin(), negit);
    int pos = distance(posit, nums.end());

    return max(neg, pos);
  }
};
```
