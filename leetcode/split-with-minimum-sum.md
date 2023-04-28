---
name: "Split with Minimum Sum"
title: "LeetCode Split with Minimum Sum Solution"
description: "Solution for the split with minimum sum problem from LeetCode."
published: "2023-03-27 PDT"
modified: "2023-03-27 PDT"
---

# Split with Minimum Sum Problem & Solution

See the [split with minimum sum problem on LeetCode](https://leetcode.com/problems/split-with-minimum-sum).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx2")

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int splitNum(int num) {
    vector<int> freq(10);
    while (num > 0) {
      ++freq[num % 10];
      num /= 10;
    }

    int num1 = 0, num2 = 0;
    bool first = true;
    for (int i = 0; i < freq.size(); ++i) {
      for (int j = 0; j < freq[i]; ++j) {
        if (first) {
          num1 = num1 * 10 + i;
        } else {
          num2 = num2 * 10 + i;
        }

        first ^= true;
      }
    }

    return num1 + num2;
  }
};
```
