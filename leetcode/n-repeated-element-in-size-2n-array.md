---
name: "N-Repeated Element in Size 2N Array"
title: "LeetCode N-Repeated Element in Size 2N Array Solution"
description: "Solution for you are given an integer array nums with the following properties: nums.length == 2 * n. nums contains n + 1 unique elements. Exactly one element of nums is repeated n times. Return the element that is repeated n times."
published: "2021-12-17 PDT"
modified: "2021-12-17 PDT"
---

# N-Repeated Element in Size 2N Array Problem & Solution

You are given an integer array `nums` with the following properties:

- `nums.length == 2 * n`.
- `nums` contains `n + 1` unique elements.
- Exactly one element of `nums` is repeated `n` times.

Return the element that is repeated `n` times.

See the [n-repeated element in size 2n array problem on LeetCode](https://leetcode.com/problems/n-repeated-element-in-size-2n-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int repeatedNTimes(vector<int>& nums) {
    for (int i = 2; i < nums.size(); ++i) {
      if (nums[i - 2] == nums[i] || nums[i - 1] == nums[i]) {
        return nums[i];
      }
    }

    return nums[0];
  }
};
```
