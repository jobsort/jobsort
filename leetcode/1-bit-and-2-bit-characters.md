---
name: "1-bit and 2-bit Characters"
title: "LeetCode 1-bit and 2-bit Characters Solution"
description: "Solution for we have two special characters: The first character can be represented by one bit 0. The second character can be represented by two bits (10 or 11). Given a binary array bits that ends with 0, return true if the last character must be a one-bit character."
published: "2021-08-21 PDT"
modified: "2021-08-21 PDT"
---

# 1-bit and 2-bit Characters Problem & Solution

We have two special characters:

- The first character can be represented by one bit 0.
- The second character can be represented by two bits (10 or 11).

Given a binary array `bits` that ends with 0, return true if the last character must be a one-bit character.

See the [1-bit and 2-bit characters problem on LeetCode](https://leetcode.com/problems/1-bit-and-2-bit-characters).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool isOneBitCharacter(vector<int>& bits) {
    for (int i = 0; i < bits.size(); ++i) {

      // Skips two positions if `bits[i]` is 1 because the next position can't be a one-bit character.
      if (bits[i] == 1) {
        i += 1;
      } else if (i == bits.size() - 1 && bits[i] == 0) {
        return true;
      }
    }

    return false;
  }
};
```
