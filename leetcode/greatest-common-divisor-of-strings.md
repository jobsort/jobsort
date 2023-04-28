---
name: "Greatest Common Divisor of Strings"
title: "LeetCode Greatest Common Divisor of Strings Solution"
description: "Solution for the greatest common divisor of strings problem from LeetCode."
published: "2022-12-06 PDT"
modified: "2022-12-06 PDT"
---

# Greatest Common Divisor of Strings Problem & Solution

See the [greatest common divisor of strings problem on LeetCode](https://leetcode.com/problems/greatest-common-divisor-of-strings).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("max-inline-insns-recursive")
#pragma GCC target("avx,avx2,fma")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  string gcdOfStrings(string str1, string str2) {
    if (str1.size() < str2.size()) {
      return gcdOfStrings(str2, str1);
    }

    if (str2.empty()) { return str1; }
    if (str1.substr(0, str2.size()) != str2) { return ""; }

    // Euclid's algorithm: gcd(a, b) = gcd(a - b, b) if a > b
    // https://en.wikipedia.org/wiki/Greatest_common_divisor
    return gcdOfStrings(str1.substr(str2.size()), str2);
  }
};
```
