---
name: "Count Pairs of Similar Strings"
title: "LeetCode Count Pairs of Similar Strings Solution"
description: "Solution for the count pairs of similar strings problem from LeetCode."
published: "2023-01-11 PDT"
modified: "2023-01-11 PDT"
---

# Count Pairs of Similar Strings Problem & Solution

See the [count pairs of similar strings problem on LeetCode](https://leetcode.com/problems/count-pairs-of-similar-strings).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int similarPairs(vector<string>& words) {
    int result = 0;

    for (int i = 0; i < words.size(); ++i) {
      vector<int> freq1('z' - 'a' + 1);
      for (auto c : words[i]) {
        ++freq1[c - 'a'];
      }

      for (int j = i + 1; j < words.size(); ++j) {
        vector<int> freq2('z' - 'a' + 1);
        for (auto c : words[j]) {
          ++freq2[c - 'a'];
        }

        int k;
        for (k = 0; k < freq1.size(); ++k) {
          if ((freq1[k] > 0 && freq2[k] == 0) ||
              (freq2[k] > 0 && freq1[k] == 0)) {
            break;
          }
        }

        if (k == freq1.size()) {
          ++result;
        }
      }
    }

    return result;
  }
};
```
