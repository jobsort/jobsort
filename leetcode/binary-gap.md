---
name: "Binary Gap"
title: "LeetCode Binary Gap Solution"
description: 'Solution for given a positive integer n, find and return the longest distance between any two adjacent 1''s in the binary representation of n. If there are no two adjacent 1''s, return 0. Two 1''s are adjacent if there are only 0''s separating them (possibly no 0''s). The distance between two 1''s is the absolute difference between their bit positions. For example, the two 1''s in "1001" have a distance of 3.'
published: "2021-12-06 PDT"
modified: "2021-12-06 PDT"
---

# Binary Gap Problem & Solution

Given a positive integer `n`, find and return the longest distance between any two adjacent `1`'s in the binary representation of `n`.
If there are no two adjacent `1`'s, return `0`.

Two `1`'s are adjacent if there are only `0`'s separating them (possibly no `0`'s).
The distance between two `1`'s is the absolute difference between their bit positions.
For example, the two `1`'s in `"1001"` have a distance of 3.

See the [binary gap problem on LeetCode](https://leetcode.com/problems/binary-gap).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){std::ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  int binaryGap(int n) {
    string s;
    while (n > 0) {
      s += n % 2 + '0';
      n /= 2;
    }

    int best = 0;
    int low = -1;
    int high = 0;
    while (high < s.size()) {
      if (s[high] == '1') {
        if (low != -1) {
          best = max(best, high - low);
        }

        low = high;
      }

      ++high;
    }

    return best;
  }
};
```
