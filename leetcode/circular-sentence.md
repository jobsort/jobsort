---
name: "Circular Sentence"
title: "LeetCode Circular Sentence Solution"
description: "Solution for the circular sentence problem from LeetCode."
published: "2023-01-24 PDT"
modified: "2023-01-24 PDT"
---

# Circular Sentence Problem & Solution

See the [circular sentence problem on LeetCode](https://leetcode.com/problems/circular-sentence).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast,unroll-loops")
#pragma GCC target("avx,avx2,fma")
#pragma GCC ivdep

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isCircularSentence(string sentence) {
    int sofar = 0, found;
    while ((found = sentence.find(' ', sofar)) != string::npos) {
      if (sentence[found - 1] != sentence[found + 1]) {
        return false;
      }

      sofar = found + 1;
    }

    return sentence.front() == sentence.back();
  }
};
```
