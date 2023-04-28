---
name: "Maximum Difference by Remapping a Digit"
title: "LeetCode Maximum Difference by Remapping a Digit Solution"
description: "Solution for the maximum difference by remapping a digit problem from LeetCode."
published: "2023-02-19 PDT"
modified: "2023-02-19 PDT"
---

# Maximum Difference by Remapping a Digit Problem & Solution

See the [maximum difference by remapping a digit problem on LeetCode](https://leetcode.com/problems/maximum-difference-by-remapping-a-digit).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC taget("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int minMaxDifference(int num) {
    string high = to_string(num), low = high;

    int i = 0;
    char c = high[i];
    while (i < high.size() && high[i] == '9') {
      c = high[i];
      ++i;
    }

    c = i < high.size() ? high[i] : '9';
    i = 0;
    while ((i = high.find(c, i)) != string::npos) {
      high.replace(i, 1, "9");
      ++i;
    }

    c = low.front();
    i = 0;
    while ((i = low.find(c, i)) != string::npos) {
      low.replace(i, 1, "0");
      ++i;
    }

    return stoi(high) - stoi(low);
  }
};
```
