---
name: "Binary Prefix Divisible by 5"
title: "LeetCode Binary Prefix Divisible by 5 Solution"
description: "Solution for the binary prefix divisible by 5 problem from LeetCode."
published: "2022-12-09 PDT"
modified: "2022-12-09 PDT"
---

# Binary Prefix Divisible by 5 Problem & Solution

See the [binary prefix divisible by 5 problem on LeetCode](https://leetcode.com/problems/binary-prefix-divisible-by-5).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("fast-math,unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<bool> prefixesDivBy5(vector<int>& nums) {
    vector<bool> results(nums.size());

    long prev = nums[0];
    results[0] = nums[0] % 5 == 0;
    for (int i = 1; i < nums.size(); ++i) {
      long prefix = 2 * prev + nums[i];
      results[i] = prefix % 5 == 0;

      // Must use modulo 5, otherwise it'll overflow.
      prev = prefix % 5;      
    }

    return results;
  }
};
```
