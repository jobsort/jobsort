---
name: "Can Place Flowers"
title: "LeetCode Can Place Flowers Solution"
description: "Solution for you have a long flowerbed in which some of the plots are planted, and some are not. However, flowers cannot be planted in adjacent plots. Given an integer array flowerbed containing 0's and 1's, where 0 means empty and 1 means not empty, and an integer n, return if n new flowers can be planted in the flowerbed without violating the no-adjacent-flowers rule."
published: "2021-09-13 PDT"
modified: "2021-09-13 PDT"
---

# Can Place Flowers Problem & Solution

You have a long flowerbed in which some of the plots are planted, and some are not.
However, flowers cannot be planted in adjacent plots.

Given an integer array `flowerbed` containing 0's and 1's, where 0 means empty and 1 means not empty, and an integer `n`, return if `n` new flowers can be planted in the `flowerbed` without violating the no-adjacent-flowers rule.

See the [can place flowers problem on LeetCode](https://leetcode.com/problems/can-place-flowers).

## C++ Solution

```cpp
#pragma GCC optimize("Ofast")
#pragma GCC optimization("unroll-loops")

static const int _=[](){ios::sync_with_stdio(false);cin.tie(nullptr);cout.tie(nullptr);return 0;}();

class Solution {
public:
  bool canPlaceFlowers(vector<int>& flowerbed, int n) {
    int j = 0;
    for (int i = 0; i < flowerbed.size(); ++i) {
      if (flowerbed[i] == 1) {
        continue;
      }

      bool left = i == 0 || (i > 0 && flowerbed[i - 1] == 0);
      bool right = i == flowerbed.size() - 1 || (i < flowerbed.size() - 1 && flowerbed[i + 1] == 0);

      if (left && right) {
        flowerbed[i] = 1;
        ++j;
      }
    }

    return j >= n;
  }
};
```
