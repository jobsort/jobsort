---
name: "Maximum Number of Balloons"
title: "LeetCode Maximum Number of Balloons Solution"
description: "Solution for the maximum number of balloons problem from LeetCode."
published: "2021-04-01 PDT"
modified: "2021-04-01 PDT"
---

# Maximum Number of Balloons Problem & Solution

See the [maximum number of balloons problem on LeetCode](https://leetcode.com/problems/maximum-number-of-balloons).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimizations("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int maxNumberOfBalloons(string text) {
    int best = numeric_limits<int>::max();
    int freq[‘z’ - ‘a’ + 1] = {};

    for (int i = 0; i < text.size(); ++i) {
      ++freq[text[i] - ‘a’];
    }

    best = min({
      freq[‘b’ - ‘a’],
      freq[‘a’ - ‘a’],
      freq[‘l’ - ‘a’] / 2,
      freq[‘o’ - ‘a’] / 2,
      freq[‘n’ - ‘a’],
    });

    return best;
  }
};
```
