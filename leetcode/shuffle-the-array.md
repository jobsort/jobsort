---
name: "Shuffle the Array"
title: "LeetCode Shuffle the Array Solution"
description: "Solution for the shuffle the array problem from LeetCode."
published: "2023-03-13 PDT"
modified: "2023-03-13 PDT"
---

# Shuffle the Array Problem & Solution

See the [shuffle the array problem on LeetCode](https://leetcode.com/problems/shuffle-the-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> shuffle(vector<int>& nums, int n) {
    vector<int> results(nums.size());

    for (int i = 0, j = n, k = 0; i < n; ++i, ++j) {
      results[k++] = nums[i];
      results[k++] = nums[j];
    }

    return results;
  }
};
```
