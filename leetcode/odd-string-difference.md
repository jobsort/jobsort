---
name: "Odd String Difference"
title: "LeetCode Odd String Difference Solution"
description: "Solution for the odd string difference problem from LeetCode."
published: "2023-01-31 PDT"
modified: "2023-01-31 PDT"
---

# Odd String Difference Problem & Solution

See the [odd string difference problem on LeetCode](https://leetcode.com/problems/odd-string-difference).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma ivdep

static const int _=[]{ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string oddString(vector<string>& words) {
    tuple<string, int, string> a{"", 0, ""}, b{"", 0, ""};

    for (auto word : words) {
      string diff;
      for (int j = 0; j < word.size() - 1; ++j) {
        diff += to_string(word[j + 1] - word[j]) + ' ';
      }

      if (get<1>(a) == 0) {
        a = {diff,1,word};
      } else if (get<0>(a) == diff) {
        ++get<1>(a);
      } else if (get<1>(b) == 0) {
        b = {diff,1,word};
      } else {
        ++get<1>(b);
      }

      if (get<1>(a) > 1 && get<1>(b) == 1) {
        return get<2>(b);
      } else if (get<1>(b) > 1 && get<1>(a) == 1) {
        return get<2>(a);
      }
    }

    if (get<1>(a) == 1) {
      return get<2>(a);
    } else {
      return get<2>(b);
    }
  }
};
```
