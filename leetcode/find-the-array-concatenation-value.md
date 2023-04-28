---
name: "Find the Array Concatenation Value"
title: "LeetCode Find the Array Concatenation Value Solution"
description: "Solution for the find the array concatenation value problem from LeetCode."
published: "2023-02-17 PDT"
modified: "2023-02-17 PDT"
---

# Find the Array Concatenation Value Problem & Solution

See the [find the array concatenation value problem on LeetCode](https://leetcode.com/problems/find-the-array-concatenation-value).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  long long findTheArrayConcVal(vector<int>& nums) {
    long long result = 0;

    int i = 0, j = nums.size() - 1;
    while (i < j) {
      int left = nums[i++], right = nums[j--];

      result += right + pow(10, floor(log10(right) + 1)) * left;
    }

    if (nums.size() % 2 == 1) {
      result += nums[i];
    }

    return result;
  }
};
```
