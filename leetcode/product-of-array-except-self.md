---
name: "Product of Array Except Self"
title: "LeetCode Product of Array Except Self Solution"
description: "Solution for the product of array except self problem from LeetCode."
published: "2022-12-21 PDT"
modified: "2022-12-21 PDT"
---

# Product of Array Except Self Problem & Solution

See the [product of array except self problem on LeetCode](https://leetcode.com/problems/product-of-array-except-self).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> productExceptSelf(vector<int>& nums) {
    vector<int> prev(nums.size(), 1),
                next(nums.size(), 1),
                results(nums.size());

    for (int i = 1; i < nums.size(); ++i) {
      prev[i] = prev[i - 1] * nums[i - 1];
    }

    for (int i = nums.size() - 2; i >= 0; --i) {
      next[i] = next[i + 1] * nums[i + 1];
    }

    for (int i = 0; i < nums.size(); ++i) {
      results[i] = prev[i] * next[i];
    }

    return results;
  }
};
```
