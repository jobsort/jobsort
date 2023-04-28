---
name: "Separate the Digits in an Array"
title: "LeetCode Separate the Digits in an Array Solution"
description: "Solution for the separate the digits in an array problem from LeetCode."
published: "2023-02-14 PDT"
modified: "2023-02-14 PDT"
---

# Separate the Digits in an Array Problem & Solution

See the [separate the digits in an array problem on LeetCode](https://leetcode.com/problems/separate-the-digits-in-an-array).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  vector<int> separateDigits(vector<int>& nums) {
    int digits = 0;
    for (int num : nums) {
      digits += floor(log10(num) + 1);
    }

    int i = 0;
    vector<int> results(digits);
    for (int num : nums) {
      digits = floor(log10(num) + 1);

      int j = 1;
      while (num > 0) {
        results[i + digits - j] = num % 10;
        num /= 10;
        ++j;
      }

      i += digits;
    }

    return results;
  }
};
```
