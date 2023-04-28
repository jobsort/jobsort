---
name: "Maximum Product Subarray"
title: "LeetCode Maximum Product Subarray Solution"
description: "Solution for the maximum product subarray problem from LeetCode."
published: "2022-12-22 PDT"
modified: "2022-12-22 PDT"
---

# Maximum Product Subarray Problem & Solution

See the [maximum product subarray problem on LeetCode](https://leetcode.com/problems/maximum-product-subarray).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int maxProduct(vector<int>& nums) {
    int low = nums[0], high = nums[0], result = nums[0];
    for (int i = 1; i < nums.size(); ++i) {
      if (nums[i] < 0) {
        swap(low, high);
      }

      low = min(nums[i], low * nums[i]);
      high = max(nums[i], high * nums[i]);

      result = max(result, high);
    }

    return result;
  }
};
```
